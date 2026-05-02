# Security Basics - Bangla

> Defensive learning notes on parser differential, MIME validation bypass, and safer `Content-Type` handling.

---

## 🔤 Basic Security Terms

| Term | বাংলা অর্থ | সহজ Example |
|---|---|---|
| Parse | বিশ্লেষণ করা, string ভেঙে অর্থ বোঝা | Pizza order slip পড়ে ingredients আলাদা করা |
| Parser | যে parse করে, যেমন program/library | দোকানদার যে order বুঝে নেয় |
| Parser Differential | দুইটা parser একই input আলাদাভাবে বোঝা | দুই ভাই মায়ের কথা আলাদাভাবে বুঝলো |
| MIME Type | File/data-এর label বা tag | Courier box-এর উপরের sticker |
| Content-Type Header | HTTP response-এর data type জানানোর header | Server বলে: “আমি এই type-এর data পাঠাচ্ছি” |
| XSS | Attacker-এর malicious JavaScript user-এর browser-এ চালানো | চিঠিতে fake note যোগ করা |
| Validation | যাচাই করা | Airport security check |
| Bypass | পাশ কাটিয়ে যাওয়া | Queue-এ ফাঁক দিয়ে সামনে যাওয়া |
| Library | Ready-made reusable code | দোকানের ready-made মসলা |
| Payload | Malicious input | Trojan Horse |
| Vulnerability | দুর্বলতা / ফাঁক | Security gap |
| Exploit | দুর্বলতার সুযোগ নেওয়া | Vulnerability use করা |

---

## 🧠 Parser Differential: মূল ধারণা

একই input → দুই parser দুইভাবে বোঝে = **Vulnerability**

### Example

```http
Content-Type: application/json;,text/html
```

Server-side parser দেখে:

```text
application/json
```

Browser দেখে:

```text
text/html
```

Result: Browser HTML render করতে পারে, ফলে XSS risk তৈরি হয়।

### কেন হয়?

- Server library অনেক সময় RFC spec strictভাবে follow করে
- Browser অনেক সময় WHATWG বা legacy behavior অনুযায়ী lenient parsing করে
- দুই parser-এর interpretation আলাদা হলে security gap তৈরি হয়

---

## 💻 Vulnerable Code Pattern

### ❌ ভুল Pattern

```js
contentType = request.args.get("type")
parsed = parseContentType(contentType)

if (parsed !== "application/json") {
  return "Invalid"
}

// BUG: raw user input response header-এ reflect হচ্ছে
response.headers["Content-Type"] = contentType
```

### ✅ Safe Pattern

```js
contentType = request.args.get("type")
parsed = parseContentType(contentType)

if (parsed !== "application/json") {
  return "Invalid"
}

// parsed / canonical value ব্যবহার করো
response.headers["Content-Type"] = parsed
```

### 🎯 Golden Rule

> যা parse/validate করেছো, সেটাই পাঠাও।  
> Raw user input কখনো reflect করো না।

---

## 🎯 MIME Validation Bypass Payload Examples

> এগুলো defensive testing ও learning purpose-এর জন্য।

### Main Payload

```http
application/json;,text/html
```

### Variations

```http
application/json;=,text/html
application/json;,text/html,=
application/json;,text/html(=
```

### কৌশল

1. Semicolon `;` দিয়ে fake parameter শুরু করা
2. Comma `,` দিয়ে দ্বিতীয় MIME type ঢোকানো
3. Browser শেষ valid MIME type নিতে পারে
4. Result হিসেবে `text/html` render হতে পারে

---

## 📜 HTTP Header Types

### List-Based Field

Comma দিয়ে multiple value থাকতে পারে।

```http
Accept: text/html, application/xml, image/png
```

### Singleton Field

শুধু একটা value থাকা উচিত।

```http
Content-Type: text/html
```

### Important Note

Spec অনুযায়ী `Content-Type` singleton field, কিন্তু browser বাস্তবে কিছু ক্ষেত্রে list-like behavior দেখাতে পারে।

---

## 📊 MIME Parser Library Comparison

### 🔴 Potentially Vulnerable

Server-side parser `application/json` accept করতে পারে, কিন্তু browser `text/html` হিসেবে render করতে পারে।

- Python: `email.message`, `cgi`, `werkzeug`, `requests`, `python-mimeparse`
- PHP: `fileeye/mimemap`, `PEAR MIME_Type`
- JavaScript: `whatwg-mimetype`, Node `util.MIMEType`, `mime-types`

### 🟡 Needs Modified Payload

- Python: `googleapiclient.mimeparse`

### 🟢 Safer Behavior

Invalid input reject / error throw করতে পারে।

- Python: `rigour.mime`
- JavaScript: Express.js Response, `content-type`, `busboy`

### 🌐 Browser Behavior

- Chromium-based browsers: Chrome, Edge, Brave
- Firefox

---

## 🔍 Chromium Parsing Quirks

### 1. Content-Type list-like treat করা

কিছু ক্ষেত্রে comma দিয়ে split করে multiple MIME member হিসেবে ধরতে পারে।

### 2. Last Match Wins

```http
application/json;,text/html
```

শেষ valid MIME হিসেবে `text/html` নেওয়া হতে পারে।

### 3. Parenthesis Trick

```http
application/json;,text/html(=
```

Chromium `(` কে comment delimiter হিসেবে ধরতে পারে, ফলে `text/html` valid হিসেবে থেকে যায়।

---

## 🎓 Key Security Lessons

1. **Parse, Don’t Reflect**  
   Parser output পাঠাও, raw input না।

2. **Spec Compliance ≠ Security**  
   Library আর browser দুইজন spec মানলেও interpretation আলাদা হতে পারে।

3. **`X-Content-Type-Options: nosniff` সবসময় যথেষ্ট না**  
   nosniff sniffing আটকায়, কিন্তু declared `Content-Type` ভুলভাবে browser parse করলে risk থাকতে পারে।

4. **Parser Differential শুধু MIME-এ না**  
   আরও জায়গায় দেখা যায়:
   - URL parsing
   - Cookie parsing
   - JSON/XML parsing
   - HTTP headers

5. **Defense**
   - Strict allowlist ব্যবহার করো
   - Validated value serialize করে পাঠাও
   - Multiple parser output compare করো
   - User input canonicalize করো
   - Raw user input response header-এ reflect করো না

---

## 🛡️ Secure Implementation Checklist

- [ ] User-controlled `Content-Type` সরাসরি response header-এ বসানো হচ্ছে না
- [ ] Parsed/canonical MIME value ব্যবহার করা হচ্ছে
- [ ] Strict allowlist আছে
- [ ] Invalid MIME syntax reject করা হচ্ছে
- [ ] Duplicate বা comma-separated `Content-Type` reject করা হচ্ছে
- [ ] Security tests-এ parser differential payload cover করা হয়েছে
- [ ] Browser behavior test করা হয়েছে
- [ ] `X-Content-Type-Options: nosniff` set করা হয়েছে
- [ ] HTML response দরকার না হলে HTML MIME allow করা হয়নি

---

## ⚡ Quick Reference

### Attack Flow

```text
1. App Content-Type validate করে
2. App raw user input response header-এ reflect করে
3. Payload পাঠানো হয়: application/json;,text/html
4. Server parser বলে: application/json
5. Browser পড়ে: text/html
6. Browser HTML render করে → XSS risk
```

### Payloads

```http
application/json;,text/html
application/json;=,text/html
application/json;,text/html,=
application/json;,text/html(=
```

### Fix

```js
response.headers["Content-Type"] = parsedValue
// not raw user input
```

---

## 🎁 সহজ Analogy

> Bouncer ID verify করেছে front দেখে,  
> কিন্তু ভেতরে back-এ অন্য তথ্য ছিল।  
> এটাই parser differential.

---

## 📚 Related Topics

- MIME parsing
- HTTP Content-Type
- Parser differential
- XSS prevention
- RFC 9110 HTTP Semantics
- WHATWG MIME Sniffing
- Secure header handling

---

## ⚠️ Disclaimer

এই README শুধুমাত্র defensive security learning, secure coding, এবং authorized testing-এর জন্য।  
Unauthorized testing বা exploitation করা উচিত নয়।

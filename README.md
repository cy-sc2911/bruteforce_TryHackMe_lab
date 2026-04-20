# 🔐 HTTP Brute Force Tool — TryHackMe Lab

> **⚠️ EDUCATIONAL PURPOSES ONLY** — Designed for authorized testing in controlled environments like TryHackMe. Unauthorized access to computer systems is illegal.

---

## 📚 Overview

This project demonstrates how **brute force attacks** work at the HTTP protocol level. It's a practical learning tool for understanding password guessing mechanisms and security vulnerabilities in web authentication systems. Built for the TryHackMe learning platform.

### Key Use Case
Automates HTTP POST requests to test weak passwords (e.g., numeric PINs) against vulnerable login forms in a controlled lab environment.

---

## 🎯 Features

- ✅ **Automated password guessing** — Systematically tests a list of passwords
- ✅ **HTTP POST requests** — Sends authentication data to web forms
- ✅ **Simple & readable code** — Easy to understand and modify for learning
- ✅ **Response validation** — Detects successful login by checking response text
- ✅ **Educational comments** — Includes ethical reminders and code explanations
- ✅ **Customizable** — Easy to adapt for different targets and wordlists

---

## 🔍 How It Works

```
1. Generates a list of 4-digit numeric passwords (0000–9999)
2. Iterates through each password
3. Sends an HTTP POST request with username + password
4. Checks if the response contains "Invalid"
5. If no "Invalid" in response → credentials found ✓
6. If "Invalid" found → tries next password
```

### Code Flow
```python
for each password in 0000-9999:
    POST { username: "admin", password: password }
    if "Invalid" NOT in response:
        print "✓ Found!"
        break
    else:
        print "✗ Trying next..."
```

---

## 💡 What I Learned

### Security Concepts
- **How brute force attacks work** at the protocol level
- **HTTP authentication vulnerabilities** and weak password policies
- **Response analysis** to detect successful login attempts

### Python Skills
- **Structuring Python scripts** for modularity and reusability
- **Error handling** for network timeouts and connection errors
- **String manipulation** and response parsing
- **Loop optimization** for iterative tasks

---

## ⚖️ Legal & Ethical Notice

### ✅ DO
- Use **only on systems you own or have explicit written permission to test**
- Test in **controlled lab environments** (TryHackMe, HackTheBox, etc.)
- Learn from this for **defensive security purposes**
- Report findings responsibly if you find vulnerabilities

### ❌ DON'T
- Attack **unauthorized targets** (illegal under CFAA and similar laws)
- Test on **production systems** without explicit permission
- Cause **disruption or data loss**
- Use for **malicious purposes**

---

## 📁 Project Structure

```
bruteforce_TryHackMe_lab/
├── app.py              # Main brute force script
├── README.md           # Documentation (this file)
└── requirements.txt    # Python dependencies (optional)
```

### Optional: Create `requirements.txt`
```bash
requests==2.31.0
```

Install with:
```bash
pip install -r requirements.txt
```

---

## 🧪 Testing & Improvement Ideas

1. **Add logging** — Write attempts to a file for analysis
2. **Implement exponential backoff** — Avoid rate limiting
3. **Use proxies** — Rotate IPs if needed
4. **Add user agents** — Bypass basic bot detection
5. **Support multiple endpoints** — Test login, admin panel, API, etc.
6. **Database integration** — Log successful credentials

---

## 📄 License

This project is provided for **educational purposes only**. Use responsibly and ethically.

---

## ❓ FAQ

**Q: Will this work on any website?**
A: No. It only works on targets with the vulnerable password validation method shown. Most real sites use rate limiting, account lockouts, and stronger validation.

**Q: Is this tool illegal?**
A: The tool itself is neutral. It's **illegal if used without authorization**. Use only on systems you own or have written permission to test.

**Q: Why use this instead of a real tool like Hydra?**
A: This project is designed for learning. Real pentesters use mature tools like Hydra, Burp Suite, or custom scripts. This is a hands-on educational starting point.

**Q: Can I use custom passwords instead of 0000-9999?**
A: Absolutely! Modify the `password_list` variable to use any wordlist.

# Project Deprecated - Migration Notice

The original `CaesarCipher.extended` Python package has been **deprecated and moved** to a new, better-organized project:

**New Hero Repository:**
https://github.com/ViratiAkiraNandhanReddy/caesarcipher-extended

**Python Package Repository:**
https://github.com/ViratiAkiraNandhanReddy/caesarcipher-extended-py

This change was made to provide a cleaner, more maintainable package structure with many new features, improved organization, better development practices, and a stronger foundation for future updates.

## Important Naming Change

Please do not be confused by the package name change.

The previous package was:

```
CaesarCipher.extended
```

The new package name is:

```
caesarcipher-extended
```

This naming change was intentional to maintain better consistency with PyPI package naming conventions and improve discoverability.

## PyPI Name Normalization Notice

Please note that installing using the old package name may still resolve to the new package because **PyPI normalizes package names**.

For example, names such as:

```bash
CaesarCipher.extended
caesarcipher-extended
caesarcipher_extended
```

are treated as equivalent by PyPI package name normalization rules.

Because of this, attempting to install the old package name from PyPI may install the newer `caesarcipher-extended` package instead.

This behavior is expected and helps maintain compatibility while transitioning to the new package naming convention.

## Apology to Existing Users

A heartfelt apology to everyone who depended on the original package.

The previous release was deleted without a proper migration notice, and we understand that this may have affected existing projects, dependency files, or application structures that relied on this library.

We sincerely apologize for the inconvenience caused.

## Temporary Installation of the Old Version

If you still need the old implementation temporarily while migrating, you can install it directly from GitHub:

```bash
pip install git+https://github.com/ViratiAkiraNandhanReddy/CaesarCipher.extended-python.pypi
```

For `requirements.txt`, use:

```txt
git+https://github.com/ViratiAkiraNandhanReddy/CaesarCipher.extended-python.pypi
```

This should provide enough time to migrate your project to the newer implementation.

## Recommended Migration

We strongly recommend moving to the new package:

* Better organized codebase
* Improved package structure
* More features
* Regular maintenance and updates
* Future security patches
* Improved developer experience
* Long-term support

The new implementation is actively maintained and will be the primary version going forward.

Thank you for your understanding, support, and patience during this transition. ❤️

---

<img src="https://cdn.jsdelivr.net/gh/ViratiAkiraNandhanReddy/pixel-art-readme-gifs@v1/gifs/hrzn/12c44bd6-f3d1-45b0-97a6-fdd24ed8062e.gif" width="100%">
<div align="center">
		<img src="https://img.shields.io/pypi/v/CaesarCipher.extended?color=blue" alt="PyPI version" />
		<img src="https://img.shields.io/github/license/ViratiAkiraNandhanReddy/CaesarCipher.extended-python.pypi" alt="License" />
	    <img src="https://api.visitorbadge.io/api/visitors?path=ViratiAkiraNandhanReddy/caesarcipher-extended&label=Repository%20Visits&style=flat" alt="Repository Visits" />
	<h1><a href="https://pypi.org/project/caesarcipher-extended/">CaesarCipher.extended</a></h1>
	<p><em>Simple, creative, and practical Caesar cipher encryption for Python projects.</em></p>
</div>

---

## 🚀 Why CaesarCipher.extended?

Ever wanted to add a layer of protection to your data without the complexity of modern cryptography? CaesarCipher.extended brings the classic Caesar cipher to Python, making it easy to obfuscate text, passwords, usernames, and more. It's not military-grade, but it's a huge step up from plain text!

---

## 🔑 What is the CaesarCipher.extended?

The Caesar cipher is one of the oldest and simplest encryption techniques. Each character in your text is shifted by a fixed number of positions. This package extends the classic algorithm to support:

- **Letters** (upper & lower case)
- **Digits** (optional)
- **Symbols** (optional)
	- Symbols <br>
	- Emojis (some support)

You choose what gets encrypted and how!

---

## ✨ Features

- Encrypt and decrypt text with a customizable shift
- Optionally include digits and symbols
- Input validation for safety
- Intuitive API for quick integration
- Perfect for small to mid-scale projects
- Much better than storing plain text

---

## 📦 Installation

Install from PyPI:

```bash
pip install CaesarCipher.extended
```

Or clone from GitHub:

```bash
git clone https://github.com/ViratiAkiraNandhanReddy/CaesarCipher.extended.git
cd CaesarCipher.extended
```

---

## 🛠️ Usage

### Encrypting Text

```python
from CaesarCipher import Encryption

# Basic encryption
enc = Encryption("Hello, World! 123")
print("Encrypted:", enc.encrypt())

# Advanced: shift everything
enc2 = Encryption("Secret123!😊", shift = 7, alterNumbers = True, alterSymbols = True)
print("Encrypted:", enc2.encrypt())
```

### Decrypting Text

```python
from CaesarCipher import Decryption

# Basic decryption
dec = Decryption("Olssv, Dvysk! 890", shift = 7, isNumbersAltered = True, isSymbolsAltered = True)
print("Decrypted:", dec.decrypt())
```

---

### File-based Encryption / Decryption

You can encrypt or decrypt files in-place using `encrypt_file()` and
`decrypt_file()` on the corresponding class instances. Both methods read
the file contents, replace the file with the transformed text, and return
a boolean indicating success.

```python
from CaesarCipher import Encryption, Decryption

# Encrypt a file in-place
enc = Encryption(shift = 4, alterNumbers = True, alterSymbols = True)
ok = enc.encrypt_file('secrets.txt')
if ok:
	print('File encrypted')

# Decrypt a file in-place
dec = Decryption(shift = 4, isNumbersAltered = True, isSymbolsAltered = True)
ok = dec.decrypt_file('secrets.txt')
if ok:
	print('File decrypted')
```

Notes:
- These methods return `False` when the file does not exist or when the
	process lacks permission to read/write the file. Other errors will
	propagate.

---

## 📚 API Reference

### Encryption

```python
Encryption(text: str, shift: int = 3, alterSymbols: bool = False, alterNumbers: bool = False)
```

- `text`: The string to encrypt
- `shift`: How many positions to shift (default: 3)
- `alterSymbols`: Shift symbols? (default: False)
- `alterNumbers`: Shift digits? (default: False)

#### `.encrypt() -> str`
Returns the encrypted string.

### Decryption

```python
Decryption(text: str, shift: int = 3, isSymbolsAltered: bool = False, isNumbersAltered: bool = False)
```

- `text`: The string to decrypt
- `shift`: How many positions to shift back (default: 3)
- `isSymbolsAltered`: Were symbols shifted? (default: False)
- `isNumbersAltered`: Were digits shifted? (default: False)

#### `.decrypt() -> str`
Returns the decrypted string.

---

## 🔍 Comparison Table

See how CaesarCipher transforms your data:

| Stage                | Example Text                |
|----------------------|---------------------------- |
| **Original**         | HelloWorld123!              |
| **After Encryption** | KhoorZruog456!              |
| **After Decryption** | HelloWorld123!              |

**How it works:**
- Encryption shifts each character by a fixed amount (default: 3).
- Decryption reverses the shift, restoring the original text.

You can customize the shift and choose to include digits and symbols for even more flexibility!

---

## ⚠️ Limitations & Security

- **Not for high-security needs!** Vulnerable to brute-force and frequency analysis.
- Symbol shifting may produce non-printable characters.
- For real password storage, use cryptographic hashes (bcrypt, Argon2, etc).

---

## 💡 When Should You Use This?

- Small to mid-scale projects
- Obfuscating sensitive data (usernames, passwords, tokens)
- Educational demos
- Quick protection for logs or configs

> 💯 : Some encryption is always better than none. This package is a practical upgrade from plain text!

---

## 🌐 Social & Links


[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/viratiakiranandhanreddy/)
[![X](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=x&logoColor=white)](https://x.com/Viratiaki53)
[![Instagram](https://img.shields.io/badge/Instagram-E1306C?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/viratiaki53)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://facebook.com/ViratiAkiraNandhanReddy)
[![Gist](https://img.shields.io/badge/Gist-2b3137?style=for-the-badge&logo=github&logoColor=white)](https://gist.github.com/ViratiAkiraNandhanReddy)
[![YouTube](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@ViratiAkiraNandhanReddy)
[![Website](https://img.shields.io/badge/Website-0077b6?style=for-the-badge&logoColor=white)](https://viratiakiranandhanreddy.github.io/CaesarCipher.extended-python.pypi/)
[![PyPI](https://img.shields.io/badge/PyPI-3775A9?style=for-the-badge&logo=pypi&logoColor=white)](https://pypi.org/project/CaesarCipher.extended/)
[![Mail](https://img.shields.io/badge/Mail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:contact.viratiakiranandhanreddy+python@gmail.com)

---

## 📝 License

<p align="center"><kbd>&copy; 2025 <a href="https://github.com/ViratiAkiraNandhanReddy">ViratiAkiraNandhanReddy</a>. This project is licensed under the <i> GNU GENERAL PUBLIC LICENSE </i>.</kbd></p>

---

## 👤 Author

### Developed by [ViratiAkiraNandhanReddy](https://github.com/ViratiAkiraNandhanReddy)

---

<h3 align="center"> Questions, suggestions, or want to contribute? Open an issue or pull request on GitHub! </h3>

<p align="center"> <img src="https://capsule-render.vercel.app/api?type=waving&color=0e8fff&height=100&section=footer" width="100%" /> </p> 

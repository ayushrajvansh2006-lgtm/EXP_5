# EXP_5

## How to decrypt

### Overview
This document provides instructions for decrypting data in the EXP_5 project.

### Prerequisites
- Python 3.x or higher
- Basic understanding of cryptography concepts

### Decryption Methods

#### Method 1: Caesar Cipher Decryption
If the data is encrypted using a Caesar cipher (shift cipher):

```python
def caesar_decrypt(encrypted_text, shift):
    decrypted = ""
    for char in encrypted_text:
        if char.isalpha():
            if char.isupper():
                decrypted += chr((ord(char) - ord('A') - shift) % 26 + ord('A'))
            else:
                decrypted += chr((ord(char) - ord('a') - shift) % 26 + ord('a'))
        else:
            decrypted += char
    return decrypted

# Example usage
encrypted_message = "KHOOR ZRUOG"
shift_value = 3
result = caesar_decrypt(encrypted_message, shift_value)
print(result)  # Output: HELLO WORLD
```

#### Method 2: ROT13 Decryption
For ROT13 encrypted text:

```python
import codecs

encrypted_text = "Uryyb Jbeyq"
decrypted_text = codecs.encode(encrypted_text, 'rot_13')
print(decrypted_text)  # Output: Hello World
```

#### Method 3: Simple XOR Decryption
For XOR-based encryption:

```python
def xor_decrypt(encrypted_text, key):
    decrypted = ""
    for i, char in enumerate(encrypted_text):
        decrypted += chr(ord(char) ^ ord(key[i % len(key)]))
    return decrypted

# Example usage
encrypted = "abc"
key = "secret"
result = xor_decrypt(encrypted, key)
print(result)
```

### File Format
- **AR_5.txt**: Contains encrypted or encoded data
- **README.md**: This documentation file

### Steps to Decrypt AR_5.txt
1. Identify the encryption method used
2. Determine the encryption key or shift value
3. Apply the appropriate decryption method
4. Verify the decrypted output

### Common Encryption Standards
- Caesar Cipher (Shift Cipher)
- ROT13
- XOR Encryption
- AES (Advanced Encryption Standard)
- Base64 Encoding/Decoding

### Base64 Decoding Example
```python
import base64

encoded_text = "SGVsbG8gV29ybGQ="
decoded_text = base64.b64decode(encoded_text).decode('utf-8')
print(decoded_text)  # Output: Hello World
```

### Troubleshooting
- If decryption fails, verify the encryption method
- Ensure the key or shift value is correct
- Check for encoding issues (UTF-8, ASCII, etc.)
- Try different shift values if using Caesar cipher

### References
- [Python Cryptography Documentation](https://cryptography.io/)
- [Caesar Cipher Explanation](https://en.wikipedia.org/wiki/Caesar_cipher)
- [XOR Encryption](https://en.wikipedia.org/wiki/XOR_cipher)

### Contact
For questions or issues, please create an issue in this repository.

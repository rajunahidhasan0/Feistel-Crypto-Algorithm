# 🔐 Feistel-Based Cryptographic Algorithm

## 📌 Overview
This project implements a **Feistel-based cryptographic algorithm** using a **32-bit key**, **LFSR-based key scheduling**, **S-Box transformation**, and **P-Box permutation** for encryption and decryption. The algorithm follows a **Feistel network structure**, ensuring reversible encryption and decryption.

🚀 **Features:**
- **Feistel Structure** for encryption and decryption
- **LFSR-Based Key Scheduling** for dynamic subkey generation
- **4×4 S-Box** for non-linearity
- **P-Box Bit Permutation** for diffusion
- **Python Implementation** with unit tests

---

## 📁 Repository Structure
```
Feistel-Crypto-Algorithm/
│── 📂 docs/                # Documentation & design details
│   ├── Feistel-Based Cryptographic Algorithm.pdf
│   ├── DESIGN.md           # Detailed design explanation
│   ├── SECURITY.md         # Security analysis
│   ├── PSEUDOCODE.md       # Pseudocode of the algorithm
│   ├── FLOWCHART.png       # Visual representation of encryption process
│
│── 📂 src/                 # Source code
│   ├── feistel_cipher.py   # Feistel encryption and decryption logic
│   ├── key_schedule.py     # Key scheduling using LFSR
│   ├── sbox.py             # S-Box functions
│   ├── pbox.py             # P-Box permutation logic
│   ├── utils.py            # Utility functions
│   ├── main.py             # Example script for encryption/decryption
│
│── 📂 tests/               # Unit tests
│   ├── test_feistel_cipher.py
│
│── .gitignore              # Ignore unnecessary files
│── LICENSE                 # License information
│── requirements.txt        # Dependencies (if any)
│── README.md               # This file (project overview)
```

---

## 🛠 Installation & Setup
### **🔹 Prerequisites**
- Python 3.x installed
- Git installed (for cloning the repository)

### **🔹 Clone the Repository**
```bash
git clone https://github.com/yourusername/Feistel-Crypto-Algorithm.git
cd Feistel-Crypto-Algorithm
```

### **🔹 Install Dependencies (if needed)**
```bash
pip install -r requirements.txt
```

---

## 🔑 How It Works
1. **Key Scheduling:**
   - A **32-bit master key** seeds an **LFSR (Linear Feedback Shift Register)**.
   - Generates **16-bit subkeys** for each encryption round.

2. **Encryption Process:**
   - Splits a **32-bit plaintext** into two **16-bit halves**.
   - Applies **S-Box substitution** and **P-Box permutation**.
   - XORs with **round subkey**.
   - Swaps halves and repeats for `N` rounds.

3. **Decryption Process:**
   - Reverses encryption using the **same subkeys in reverse order**.
   - Uses the **inverse S-Box and P-Box** to restore the original plaintext.

---

## 🔄 Usage
### **Encrypt a 32-bit Block**
```python
from feistel_cipher import encrypt_block

plaintext = 0x12345678
key = 0xA1B2C3D4  # 32-bit master key
ciphertext = encrypt_block(plaintext, key)

print(f"Ciphertext: {hex(ciphertext)}")
```

### **Decrypt a 32-bit Block**
```python
from feistel_cipher import decrypt_block

decrypted = decrypt_block(ciphertext, key)
print(f"Decrypted: {hex(decrypted)}")
```

---

## ✅ Unit Testing
Run unit tests to verify encryption and decryption:
```bash
python tests/test_feistel_cipher.py
```
If successful, you'll see:
```
All tests passed!
```

---

## 📊 Security Analysis
- 🔹 **Brute Force Attack Resistance:**  
  - 32-bit key space (4.29 billion keys).
- 🔹 **Non-linearity via S-Box:**  
  - Protects against **linear cryptanalysis**.
- 🔹 **Diffusion via P-Box:**  
  - Ensures small changes affect multiple bits (avalanche effect).
- 🔹 **LFSR Key Scheduling:**  
  - Generates dynamic subkeys, making **related-key attacks difficult**.

For a deeper analysis, see [`SECURITY.md`](docs/SECURITY.md).

---

## 🔥 Future Improvements
- Implement a **larger key size (e.g., 64-bit)** for stronger encryption.
- Optimize **S-Box generation** for improved security.
- Implement **GUI or CLI tool** for user-friendly encryption.

---

## 🤝 Contributing
Want to improve this cryptographic algorithm? Feel free to contribute:
1. **Fork the repository**
2. **Create a new branch (`feature-improvement`)**
3. **Commit changes & push**
4. **Open a Pull Request (PR)**

---

## 📧 Contact
📌 **Author:** Md Nahid Hasan  
📌 **Email:** rajunahidhasan0@gmail.com  
📌 **GitHub:** [rajunahidhasan0](https://github.com/rajunahidhasan0)  

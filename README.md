# File Integrity Verification on Windows (SHA-256)

## Objective
Demonstrate how cryptographic hash functions verify file integrity and how tampering is detected.

## Steps Performed
1️⃣ Created a text file: file.txt  
2️⃣ Generated its SHA-256 hash using PowerShell:
   Get-FileHash file.txt -Algorithm SHA256

3️⃣ Modified the file (simulated integrity attack).
4️⃣ Generated the hash again.
5️⃣ Compared both hashes.

## Results
- Original Hash: <paste hash here>
- Tampered Hash: <paste hash here>

➡️ The hashes were DIFFERENT, proving the file was altered.

## Explanation
Cryptographic hash functions (like SHA-256) produce a unique fingerprint of a file.  
Even changing a single character completely changes the hash.

Integrity attacks are detected by comparing:
- Stored “known-good” hash
- Newly calculated hash

✔️ Match → file is safe  
❌ Mismatch → file was modified

## Real-World Uses
- Software download verification  
- Digital forensics  
- Secure backups  
- Package managers (npm, pip, apt)

## Conclusion
Hash verification is a simple and powerful way to detect file tampering and ensure file integrity.

## 🚀 Future Work
This process can be automated. A script can calculate a file’s hash and automatically compare it with a trusted checksum.  
For example, many Linux distributions publish SHA-256 checksums for ISO downloads. After downloading, we can compute the hash locally and verify it against the published value. If they don’t match, the file is either corrupted or has been tampered with.

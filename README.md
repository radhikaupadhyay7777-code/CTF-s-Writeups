# CTF Write-ups | Cybersecurity Portfolio

A collection of my Capture The Flag (CTF) investigations and write-ups, covering **cryptography**, **digital forensics**, **steganography**, **encoding**, and related security techniques.

I document the problem, the vulnerability or clue, tools used, the solving approach, the outcome, and what I learned. **Completed challenges and ongoing investigations are kept separate.**

> **Publication note:** These notes are reconstructed from my documented challenge work. I will add original screenshots and scripts as available. I only publish full flags after checking the event's write-up and disclosure rules.

## Solved challenges

| Challenge | Category | Write-up |
|---|---|---|
| The Forgotten Vault | AES-128 / weak key derivation | [Read](Cryptography/The-Forgotten-Vault.md) |
| Pirate Multilayer Encoding | Base62 / Base58 / Base32 | [Read](Cryptography/Pirate-Multilayer-Encoding.md) |
| Poison ECC Fault Attack | Elliptic-curve fault analysis | [Read](Cryptography/Poison-ECC-Fault-Attack.md) |
| Deleted Pirate Journal | E01 / NTFS / Vigenère | [Read](Digital-Forensics/Deleted-Pirate-Journal.md) |
| Operation Dead Drop | Image LSB / Base32 | [Read](Steganography/Operation-Dead-Drop.md) |

## Ongoing / unresolved investigations

| Challenge | Category | Notes |
|---|---|---|
| Cursed Encryption Oracle | Chosen-plaintext cryptography | [Read](Investigations/Cursed-Encryption-Oracle.md) |
| ARGON: The Silent Vault | ECDSA / lattices / RSA / Argon2id | [Read](Investigations/ARGON-The-Silent-Vault.md) |
| HACKITUP Logo | JPEG steganography | [Read](Investigations/HACKITUP-Logo-Steganography.md) |
| Webhack Solutions QR | QR / OSINT | [Read](Investigations/Webhack-Solutions-QR.md) |
| Westbound | Network forensics | [Read](Investigations/Westbound.md) |

## Tools & skills

Python, Kali Linux, CyberChef, Wireshark, Sleuth Kit (`fls`, `icat`, `mmls`), libewf, Binwalk, ExifTool, StegSeek, cryptographic primitives, and cryptanalysis.

## Repository structure

```text
CTF-Writeups/
├── README.md
├── Cryptography/
│   ├── The-Forgotten-Vault.md
│   ├── Pirate-Multilayer-Encoding.md
│   └── Poison-ECC-Fault-Attack.md
├── Digital-Forensics/
│   └── Deleted-Pirate-Journal.md
├── Steganography/
│   └── Operation-Dead-Drop.md
├── Investigations/
│   ├── Cursed-Encryption-Oracle.md
│   ├── ARGON-The-Silent-Vault.md
│   ├── HACKITUP-Logo-Steganography.md
│   ├── Webhack-Solutions-QR.md
│   └── Westbound.md
├── Scripts/
│   └── aes_vault_solver.py
└── Screenshots/
```

## Reproducing the AES vault solve

The sample solver in [`Scripts/aes_vault_solver.py`](Scripts/aes_vault_solver.py) takes a dictionary file and the original hexadecimal ciphertext (embedded in the script). Install `pycryptodome` and run:

```bash
python3 -m pip install pycryptodome
python3 Scripts/aes_vault_solver.py /path/to/wordlist.txt
```

For the other challenges, see individual write-ups for available reproduction details and limitations.

## Ethics

All techniques described here were applied in authorized CTF/lab environments. Challenge flags and challenge-host details should not be used outside those environments. Please follow event publication policies.

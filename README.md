# cipher-ai-analysis

Statistical analysis tools for classical cipher breaking and AI-generated text fingerprinting.

**Jamie Grunewald** | [LinkedIn](https://www.linkedin.com/in/jamielg) | [github.com/JamieGrunewald](https://github.com/JamieGrunewald)

---

## Overview

This repository applies statistical text analysis techniques across two domains:

1. **Classical Cipher Breaking** — frequency analysis, Index of Coincidence, and chi-square scoring to break polyalphabetic ciphers without prior knowledge of the key.
2. **AI Text Fingerprinting** *(in development)* — extending the same statistical foundations to detect authorship signatures in AI-generated text.

The cipher analysis module originated as a live demo for the CypherCon 9 talk **"Breaking Ciphers & Fingerprinting AI"** (Milwaukee, April 2026), based on graduate cryptography research at the University of Delaware (CPEG 472).

---

## Repository Structure

```
cipher-ai-analysis/
├── cipher_analysis/
│   ├── cyphercon_demo.py     # Live demo: break a Vigenère-encrypted WarGames quote
│   ├── words.txt             # English word list for plaintext scoring
│   └── sample_output.txt     # Reference output from a clean run
├── ai_fingerprinting/        # Coming soon
└── README.md
```

---

## Cipher Analysis

### The Attack Pipeline

A complete Vigenère cipher break executed in seven steps:

| Step | Technique | Purpose |
|------|-----------|---------|
| 1 | Ciphertext display | Establish the problem |
| 2 | IOC + Chi-Square | Statistical recon — identify cipher type |
| 3 | IOC column sweep | Determine key length |
| 4 | Per-column frequency attack | Recover alphabetic key characters |
| 5 | Word-list disambiguation | Resolve chi-square near-ties |
| 6 | Key reconstruction | Reveal the full key |
| 7 | Plaintext recovery | Decrypt the ciphertext |

### Running the Demo

**Requirements:** Python 3.8+, no external dependencies.

```bash
# Interactive mode (press ENTER to advance each step)
python3 cipher_analysis/cyphercon_demo.py

# Auto mode (timed pauses — useful for recording)
python3 cipher_analysis/cyphercon_demo.py --auto
```

`words.txt` must be in the same directory as the script.

---

## AI Fingerprinting *(coming soon)*

The same statistical patterns that expose a repeating cipher key also expose authorship signatures in text. The planned module will apply IOC, character frequency distributions, and stylometric scoring to compare text samples and identify AI-generated content.

---

## Background

The cipher analysis pipeline mirrors the full implementation in the [Crypto](https://github.com/JamieGrunewald/Crypto) repository (CPEG 472 coursework). The demo script is self-contained for portability.

---

## License

MIT License — see [LICENSE](LICENSE)

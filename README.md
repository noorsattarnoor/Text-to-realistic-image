# Text → Realistic Image Encryption (Encrypt-then-Camouflage)

This project converts plaintext (TXT/DOCX) into a grayscale cipher image and then camouflages it inside a photorealistic RGB cover using an α-blend. The process is exactly reversible: with the manifest and the correct key, the original text is fully recovered (SHA-256 match).

Key steps: key-dropped 16×16 ASCII substitution → V-stream nibble shifts → dynamic checksum → (optional) Arnold Cat Map → XOR diffusion → Lorenz-based index permutation → α-blend with cover.

Data folders:
text to test/ — input texts (TXT/DOCX)
Images to test/ — cover images (PNG/JPG)

Quick start: open `Encryption and decryption code.ipynb`, run cells in order. The notebook auto-discovers files from the two folders (alphabetical pairing), generates the fake images, and writes `encryption_manifest.json`. Then run the decryption cells to restore the cipher and the plaintext (hash MATCH expected).

Notes: 
1. Use lossless outputs; avoid re-encoding; do not publish real encryption_manifest.json (it contains the key in hex).
2. ([Click here](https://colab.research.google.com/github/noorsattarnoor/Text-to-realistic-image/blob/main/Encryption%20and%20decryption%20code.ipynb)) To run the code using Google Colab website.
3. ([Click here](https://github.com/noorsattarnoor/Text-to-realistic-image/tree/main)) To run the code using Google Colab website.

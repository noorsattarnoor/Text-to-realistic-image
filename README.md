# Text → Realistic Image Encryption (Encrypt-then-Camouflage)

This project converts plaintext (TXT/DOCX) into a grayscale cipher image and then camouflages it inside a photorealistic RGB cover using an α-blend. The process is exactly reversible: with the manifest and the correct key, the original text is fully recovered (SHA-256 match).

Key steps: key-dropped 16×16 ASCII substitution → V-stream nibble shifts → dynamic checksum → (optional) Arnold Cat Map → XOR diffusion → Lorenz-based index permutation → α-blend with cover.

To run:
 Download sample files:
  * Text to be tested/ — input texts (.txt / .docx)
  * Images to be tested/ — cover images (.png / .jpg)
  Or use your own texts and images.

Quick Start
1. Open `Text-to-realistic-image2.ipynb` and run the cells in order.
2. When prompted, choose exactly five text files and five cover images for encryption.
3. The notebook will save all decryption parameters to `encryption_manifest.json`.
4. Run the decryption cells to restore the cipher image and plaintext (hash MATCH expected).
5. During decryption, all required settings are loaded automatically from `encryption_manifest.json`—no manual input needed.

([Click here](https://colab.research.google.com/github/noorsattarnoor/Text-to-realistic-image/blob/main/Text-to-realistic-image2.ipynb#scrollTo=o3EH80YCiLw3)) To run the code using Google Colab website.

# WaveQuant — Deterministic Integer Arithmetic Engine

**Claim:**  
Full-precision (FP64) numerical reconstruction achieved using integer arithmetic (INT8/INT32) only.  
No floating-point operations were performed during encoding or decoding.

---

## Proof Summary

**Reference matrix:** `W.npy`  
**Integer stream:** `stream_5.551115123125783e-17_1.npz`  

**Verification results (internal audit):**
- RMSE = 0.0  
- MAE  = 0.0  
- `array_equal = true`  
- Stream SHA1 = `4775d9b6b1a3818dcb3db3c325bd05e04e49cda3`

These values demonstrate byte-for-byte equality between the original FP64 tensor and its reconstruction from the integer stream.

---

## What the Files Represent

- **`W.npy`** – the original 64-bit floating-point matrix.  
- **`stream_…npz`** – its integer-only encoding, constructed from discrete numerators and prime-based denominators.  
  The file contains no floating-point data and no code; it is a sealed numerical container proving the result.

Together, these artifacts form a cryptographic proof of lossless integer reconstruction.  
Their SHA hashes bind the claim permanently: any identical pair of files will always yield the same equality metrics.

---

## How the Proof Is Validated

The verification was executed using the proprietary WaveQuant verifier.  
During that process, the integer stream was decoded and compared to the reference matrix, producing the zero-error metrics listed above.

Because both artifacts and their checksums are public, anyone can confirm:
1. The files are unaltered (`sha256sum` matches).  
2. The reported metrics correspond exactly to this release.

No WaveQuant source code or algorithmic details are required to confirm authenticity.

---

## About `run_demo.sh`

The included shell script records the exact command line used to generate these verified results.  
It is provided for documentation only and does **not** expose any encoding logic or proprietary methods.

---

**Contact:**  
matthew.j.curreri@gmail.com

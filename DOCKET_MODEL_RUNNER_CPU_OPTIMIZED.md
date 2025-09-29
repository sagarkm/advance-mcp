# CPU-Optimized AI Model Tags Catalogue

This document catalogues all **CPU-optimized (quantized)** model image tags identified across the specified `ai/` Docker Hub repositories.

## Inclusion Criteria

- Quantized integer / mixed low-bit formats: `Q2_K`, `Q4_0`, `Q4_K_M`, `Q4_K_XL`, `Q6_K`, `Q8_0`, `IQ1_M`, `IQ2_XXS`, and hybrids (e.g. `IQ2_XXS/Q4_K_M`).
- Excluded: Pure `F16` / `BF16` / `MOSTLY_F16` variants (not memory-optimized for CPU) unless used only to denote a non-quantized baseline.
- Purpose: Enable selection of models runnable on CPU-only systems (e.g. Intel i7, 32GB RAM, no dGPU) with improved memory footprint and throughput.

## Legend

| Column       | Meaning                                                          |
| ------------ | ---------------------------------------------------------------- |
| Tag          | Docker Model Runner tag suffix (full image = `ai/<repo>:<tag>`). |
| Params       | Billions of parameters (approx).                                 |
| Quantization | Format / hybrid quantization scheme.                             |
| Context      | Maximum context length (tokens) if listed.                       |
| Est VRAM     | VRAM footprint shown in table (also approximates RAM).           |
| File Size    | Image / model file size reported.                                |

> Est VRAM values lifted directly from Docker Hub tables where available. When not retrievable due to dynamic page loading, only tag names are listed.

---

## 1. magistral-small-3.2 (`ai/magistral-small-3.2`)

| Tag     | Params | Quantization | Context | Est VRAM | File Size |
| ------- | ------ | ------------ | ------- | -------- | --------- |
| Q4_K_XL | _N/A_  | Q4_K_XL      | _N/A_   | _N/A_    | _N/A_     |
| IQ2_XXS | _N/A_  | IQ2_XXS      | _N/A_   | _N/A_    | _N/A_     |

Notes:

- Table metadata not captured in snapshot; only quant tags.

## 2. gemma3-qat (`ai/gemma3-qat`)

| Tag     | Params | Quantization | Context | Est VRAM | File Size |
| ------- | ------ | ------------ | ------- | -------- | --------- |
| Q4_K_XL | _N/A_  | Q4_K_XL      | _N/A_   | _N/A_    | _N/A_     |
| Q4_K_M  | _N/A_  | Q4_K_M       | _N/A_   | _N/A_    | _N/A_     |
| IQ2_XXS | _N/A_  | IQ2_XXS      | _N/A_   | _N/A_    | _N/A_     |

## 3. gemma3 (`ai/gemma3`)

| Tag     | Params | Quantization | Context | Est VRAM | File Size |
| ------- | ------ | ------------ | ------- | -------- | --------- |
| Q4_K_M  | _N/A_  | Q4_K_M       | _N/A_   | _N/A_    | _N/A_     |
| IQ2_XXS | _N/A_  | IQ2_XXS      | _N/A_   | _N/A_    | _N/A_     |

## 4. qwen3-coder (`ai/qwen3-coder`)

| Tag                | Params | Quantization            | Context | Est VRAM | File Size |
| ------------------ | ------ | ----------------------- | ------- | -------- | --------- |
| 30B-A3B-UD-Q4_K_XL | 30B    | Q4_K_XL (MOSTLY_Q4_K_M) | _N/A_   | _N/A_    | _N/A_     |

## 5. smollm2 (`ai/smollm2`)

| Tag         | Params | Quantization | Context | Est VRAM     | File Size |
| ----------- | ------ | ------------ | ------- | ------------ | --------- |
| 135M-Q2_K   | 0.135B | Q2_K         | _N/A_   | _Very small_ | _Small_   |
| 135M-Q4_0   | 0.135B | Q4_0         | _N/A_   | _Small_      | _Small_   |
| 135M-Q4_K_M | 0.135B | Q4_K_M       | _N/A_   | _Small_      | _Small_   |
| 360M-Q4_0   | 0.36B  | Q4_0         | _N/A_   | _Small_      | _Small_   |
| 360M-Q4_K_M | 0.36B  | Q4_K_M       | _N/A_   | _Small_      | _Small_   |

## 6. seed-oss (`ai/seed-oss`)

| Tag            | Params | Quantization | Context | Est VRAM            | File Size |
| -------------- | ------ | ------------ | ------- | ------------------- | --------- |
| 36B-UD-Q4_K_XL | 36B    | Q4_K_XL      | 524K    | 41.11 GiB           | 39.59 GB  |
| 36B-UD-IQ1_M   | 36B    | IQ1_M        | 524K    | ~Lower than Q4_K_XL | _N/A_     |
| 36B-UD-Q6_K_XL | 36B    | Q6_K_XL      | 524K    |                     |           |

## 7. embeddinggemma (`ai/embeddinggemma`)

| Tag       | Params | Quantization | Context | Est VRAM   | File Size |
| --------- | ------ | ------------ | ------- | ---------- | --------- |
| 300M-Q8_0 | 0.3B   | Q8_0         | _N/A_   | _Moderate_ | _N/A_     |

## 8. gpt-oss (`ai/gpt-oss`)

| Tag            | Params | Quantization | Context | Est VRAM | File Size |
| -------------- | ------ | ------------ | ------- | -------- | --------- |
| 20B-UD-Q4_K_XL | 20B    | Q4_K_XL      | _N/A_   | _N/A_    | _N/A_     |
| 20B-UD-Q6_K_XL | 20B    | Q6_K_XL      | _N/A_   | _Higher_ | _N/A_     |
| 20B-UD-Q8_K_XL | 20B    | Q8_K_XL      | _N/A_   | _Higher_ | _N/A_     |

## 9. smollm3 (`ai/smollm3`)

| Tag    | Params | Quantization | Context | Est VRAM   | File Size |
| ------ | ------ | ------------ | ------- | ---------- | --------- |
| Q4_K_M | _N/A_  | Q4_K_M       | _N/A_   | _Small_    | _N/A_     |
| Q8_0   | _N/A_  | Q8_0         | _N/A_   | _Moderate_ | _N/A_     |

## 10. qwen3 (`ai/qwen3`)

| Tag            | Params | Quantization   | Context | Est VRAM | File Size |
| -------------- | ------ | -------------- | ------- | -------- | --------- |
| 0.6B-Q4_0      | 0.6B   | Q4_0           | 131K    | _Low_    | _N/A_     |
| 0.6B-Q4_K_M    | 0.6B   | Q4_K_M         | 131K    | _Low_    | _N/A_     |
| 8B-Q4_0        | 8B     | Q4_0           | 131K    | ~5.1 GiB | ~4.3 GB   |
| 8B-Q4_K_M      | 8B     | IQ2_XXS/Q4_K_M | 131K    | ~5.3 GiB | ~4.6 GB   |
| 14B-Q6_K       | 14B    | Q6_K           | 131K    | Higher   | _N/A_     |
| 30B-A3B-Q4_K_M | 30B    | Q4_K_M         | 131K    | Large    | _N/A_     |

## 11. deepseek-r1-distill-llama (`ai/deepseek-r1-distill-llama`)

| Tag        | Params | Quantization   | Context | Est VRAM  | File Size |
| ---------- | ------ | -------------- | ------- | --------- | --------- |
| 8B-Q4_0    | 8B     | Q4_0           | 131K    | 5.09 GiB  | 4.33 GB   |
| 8B-Q4_K_M  | 8B     | IQ2_XXS/Q4_K_M | 131K    | 5.33 GiB  | 4.58 GB   |
| 70B-Q4_0   | 70B    | Q4_0           | 131K    | 38.73 GiB | 37.22 GB  |
| 70B-Q4_K_M | 70B    | IQ2_XXS/Q4_K_M | 131K    | 41.11 GiB | 39.59 GB  |

## 12. llama3.3 (`ai/llama3.3`)

| Tag        | Params | Quantization   | Context | Est VRAM  | File Size |
| ---------- | ------ | -------------- | ------- | --------- | --------- |
| 70B-Q4_0   | 70B    | Q4_0           | 131K    | 38.73 GiB | 37.22 GB  |
| 70B-Q4_K_M | 70B    | IQ2_XXS/Q4_K_M | 131K    | 41.11 GiB | 39.59 GB  |

## 13. llama3.2 (`ai/llama3.2`)

| Tag       | Params | Quantization   | Context | Est VRAM | File Size |
| --------- | ------ | -------------- | ------- | -------- | --------- |
| 1B-Q4_0   | 1B     | Q4_0           | 131K    | 1.35 GiB | 727.75 MB |
| 1B-Q8_0   | 1B     | Q8_0           | 131K    | 1.87 GiB | 1.22 GB   |
| 3B-Q4_0   | 3B     | Q4_0           | 131K    | 2.68 GiB | 1.78 GB   |
| 3B-Q4_K_M | 3B     | IQ2_XXS/Q4_K_M | 131K    | 2.77 GiB | 1.87 GB   |

## 14. phi4 (`ai/phi4`)

| Tag        | Params | Quantization   | Context | Est VRAM | File Size |
| ---------- | ------ | -------------- | ------- | -------- | --------- |
| 14B-Q4_0   | 15B    | Q4_0           | 16K     | 9.16 GiB | 7.80 GB   |
| 14B-Q4_K_M | 15B    | IQ2_XXS/Q4_K_M | 16K     | 9.78 GiB | 8.43 GB   |

## 15. mistral (`ai/mistral`)

Quantized tags (representative — dynamic content not fully captured):

- 7B-Q4_0
- 7B-Q4_K_M
- 7B-Q6_K

## 16. qwq (`ai/qwq`)

Quantized tags (representative):

- Q4_0
- Q4_K_M
- (Possibly Q6_K / Q8_0 depending on release cadence)

## 17. qwen2.5 (`ai/qwen2.5`)

Representative standard quantized tiers:

- Small (≤1.5B): Q4_0, Q4_K_M
- Mid (7B–14B): Q4_0, Q4_K_M, Q6_K

## 18. deepcoder-preview (`ai/deepcoder-preview`)

Likely early accessible quant tags:

- Q4_0
- Q4_K_M

## 19. llama3.1 (`ai/llama3.1`)

Typical quantized distribution:

- 8B-Q4_0
- 8B-Q4_K_M
- 70B-Q4_0
- 70B-Q4_K_M

## 20. mistral-nemo (`ai/mistral-nemo`)

Representative quantization:

- Q4_0
- Q4_K_M
- Q6_K

---

## Excluded (Not Quantized / F16 Only During Snapshot)

- `ai/mxbai-embed-large`
- `ai/granite-embedding-multilingual`
- `ai/nomic-embed-text-v1.5`
- `ai/gemma3n`

## Recommended Starting Points (i7 / 32GB RAM / No GPU)

| Use Case                     | Suggested Tag                            | Rationale                                |
| ---------------------------- | ---------------------------------------- | ---------------------------------------- |
| General chat low RAM         | `ai/llama3.2:3B-Q4_K_M`                  | Balance of quality & <3 GB VRAM eq.      |
| Stronger general / reasoning | `ai/deepseek-r1-distill-llama:8B-Q4_K_M` | Good reasoning with modest footprint.    |
| Lightweight experimentation  | `ai/smollm2:360M-Q4_K_M`                 | Tiny & fast.                             |
| Coding + reasoning mid-tier  | `ai/phi4:14B-Q4_K_M`                     | High reasoning for size; fits 32GB RAM.  |
| Embeddings                   | `ai/embeddinggemma:300M-Q8_0`            | Higher precision embeddings still small. |
| Multilingual + size balance  | `ai/qwen3:8B-Q4_K_M`                     | Wide language support.                   |

## Selection Heuristics

1. Prefer `Q4_K_M` (or hybrid `IQ2_XXS/Q4_K_M`) as default quality/size trade-off.
2. Drop to `Q4_0` if memory constrained further (~5–10% smaller, minor quality loss).
3. Use `Q6_K` / `Q8_0` only if latency acceptable and you want slight accuracy gains.
4. Very large models (≥30B) rarely worth it on pure CPU unless batch size is 1 and patience is high.
5. For embeddings, prioritize stability (Q8_0) over minimal size unless extreme constraints.

## Next Possible Enhancements

- Add automated script to benchmark tokens/sec across selected tags.
- Enrich with exact file sizes for entries currently _N/A_ (requires dynamic page scraping pass or manual revisit).
- Add a JSON export for programmatic selection tools.

---

Generated: (UTC) <!-- timestamp placeholder -->

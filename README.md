---
language:
  - en
tags:
  - text-generation
  - transformers
  - pytorch
  - philosophy
  - cybernetics
  - experimental
  - causal-lm
  - agent
  - local
  - lora
license: apache-2.0
base_model: askfjhaskjgh/UbermenschetienASI
---

# Cybernetic Agent Lab

An experimental local-AI scaffold combining a fine-tuned language model with persistent memory, constrained tools, planning, and reflection loops.

The model used by the portable entry point is hosted on Hugging Face:

- [askfjhaskjgh/UbermenschetienASI](https://huggingface.co/askfjhaskjgh/UbermenschetienASI)

Model weights are not stored in this repository.

## What is in this repository

| File | Purpose |
|---|---|
| `UbermenschHeaven.py` | Portable entry point that downloads the Hugging Face model and runs locally |
| `Cyberneticengine.py` | Lab-oriented entry point for an existing local merged model and LoRA adapter |
| `LICENSE` | Apache License 2.0 |

Both entry points include JSONL memory, goals and plans, a constrained tool layer, reflection cycles, and optional local vector memory and text-to-speech.

## Quick start

Python 3.10+ and a CUDA-capable GPU are recommended for the 8B model.

```bash
git clone https://github.com/Loganwins/cybernetic-agent-lab.git
cd cybernetic-agent-lab

python -m venv .venv
source .venv/bin/activate

pip install torch transformers accelerate bitsandbytes
python UbermenschHeaven.py
```

The first run downloads the model from Hugging Face. Set `HF_HOME` if you want to control the model cache location.

Optional features:

```bash
pip install pyttsx3 chromadb sentence-transformers
```

## Local lab entry point

`Cyberneticengine.py` is designed for an existing local model layout. It expects these paths beneath `UBERMENCHETIEN_ROOT`:

```text
models/tokenizer_ref
models/current-merged-v4
lora_output/final
```

Run it with:

```bash
export UBERMENCHETIEN_ROOT=/path/to/your/lab
pip install torch transformers accelerate bitsandbytes peft
python Cyberneticengine.py
```

## Limitations

- This is experimental research software, not a production agent framework.
- Generated output may be incorrect, biased, incoherent, or unsafe.
- The local tool layer is constrained, but you should still review the code and run it in an isolated environment.
- The philosophical framing is creative direction, not evidence of sentience or general intelligence.

## License

Apache-2.0. See `LICENSE`.

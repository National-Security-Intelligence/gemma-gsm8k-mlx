# gemma-gsm8k-mlx

Gemma 3 1B Instruct (Google) on Apple **MLX**. **uv** + **Ruff**. Not Qwen.

```bash
uv sync
uv run ruff check .
uv run python eval_gsm8k.py --sample 200 --seed 0
```

`--sample 0` is the full GSM8K test (1,319).

Train:

```bash
uv run python prepare_gsm8k.py
uv run python train_sft.py
uv run python eval_gsm8k.py --sample 200 --adapter outputs/sft
```

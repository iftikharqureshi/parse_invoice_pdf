# Invoice Parser Lab

A short notebook that uploads an invoice PDF to OpenAI, asks the model to extract the text, and returns a structured JSON payload you can inspect.

- **Files**: `parse_pdf.ipynb` (walkthrough) and `invoice.pdf` (sample input).
- **Stack**: Python with the `openai` SDK; run in a notebook environment (e.g., Jupyter).

## Quick start
1) Install deps: `pip install openai jupyter` (or add to your existing env).
2) Set credentials: export `OPENAI_API_KEY` in your shell.
3) Launch: `jupyter notebook parse_pdf.ipynb` and execute cells top-to-bottom.

## What the notebook does
- Creates an OpenAI client from your env var.
- Uploads the sample invoice PDF as `user_data`.
- Sends a prompt (using `gpt-5-mini`) to extract fields like invoice metadata, billing details, line items, and totals, expecting raw JSON back.
- Parses and pretty-prints the JSON for review.

## Reviewer notes
- Check that the model choice and prompt structure match your accuracy/cost goals.
- Verify the returned JSON fields cover your downstream needs (discounts, taxes, credits, etc.).
- Swap `invoice.pdf` with another sample to gauge robustness.
- Ensure API keys stay out of source control; the notebook expects them in env vars only.

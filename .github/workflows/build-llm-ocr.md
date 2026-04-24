---
on:
  workflow_dispatch:

engine: copilot

permissions:
  contents: read
  issues: read
  pull-requests: read

safe-outputs:
  create-pull-request:
  add-comment:
  create-issue:

tools:
  edit: {}
  bash: true
  github: {}
---

# Build LLM OCR From Image

You are GitHub Copilot acting as an AI software engineer.

Build a complete Python project named "LLM OCR from Image".

Create:
- README.md
- requirements.txt
- .env.example
- .gitignore
- src/ocr_llm.py
- app.py
- samples/README.md
- tests/test_basic.py

Requirements:
- Use Python.
- Use OpenAI-compatible API.
- Use environment variable OPENAI_API_KEY.
- Support image path input.
- Extract text from image using multimodal LLM.
- Return JSON output.
- Detect language.
- Summarize extracted content.
- Provide confidence notes.
- Save result to outputs/ocr_result.json.
- Add CLI usage.
- Add simple Streamlit UI.
- Add error handling.
- Do not expose API keys.

CLI example:
python src/ocr_llm.py --image samples/sample.png --output outputs/ocr_result.json

Streamlit example:
streamlit run app.py

After creating the solution:
1. Run basic validation if possible.
2. Update README with setup and usage.
3. Create a pull request with all generated files.
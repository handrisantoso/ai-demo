---
on:
  workflow_dispatch:

engine: claude

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

# Build Claude Vision OCR From Image

You are Claude acting as a senior AI software engineer.

Build a complete Python project named "Claude Vision OCR From Image".

The project must use Anthropic Claude API to extract text directly from images.

Do not use:
- Tesseract
- Ollama
- OpenAI API
- Gemini API
- Local OCR engines

Use:
- Python 3.10+
- anthropic
- python-dotenv
- pillow
- streamlit
- pydantic
- pytest

Environment variable:
ANTHROPIC_API_KEY

Default model:
claude-3-5-sonnet-latest

Required files:
- README.md
- requirements.txt
- .env.example
- .gitignore
- src/claude_ocr.py
- src/utils.py
- app.py
- tests/test_basic.py
- samples/README.md
- outputs/.gitkeep

CLI:
python src/claude_ocr.py --image samples/sample.png --output outputs/ocr_result.json

Streamlit:
streamlit run app.py

The OCR result must be JSON:

{
  "source_file": "...",
  "detected_language": "...",
  "detected_text": "...",
  "tables_markdown": "...",
  "summary": "...",
  "confidence_notes": "...",
  "warnings": [],
  "model": "claude-3-5-sonnet-latest"
}

The Claude prompt must instruct:
- extract all visible text
- preserve line breaks
- preserve table structure as markdown
- identify unreadable parts
- avoid hallucination
- return valid JSON only

Add error handling for:
- missing image
- unsupported image format
- missing ANTHROPIC_API_KEY
- API errors
- invalid JSON response

README must include:
- Windows setup
- how to create .env
- CLI usage
- Streamlit usage
- sample output
- troubleshooting
- GitHub Agentic Workflow explanation

After creating files:
1. Run syntax check.
2. Run pytest if possible.
3. Create a pull request titled:

Build Claude Vision OCR from image demo
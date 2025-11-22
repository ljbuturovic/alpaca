# alpaca

A simple command-line tool to list available LLM models from various providers (OpenAI, Google, Anthropic, xAI).

## Installation

1. Clone the repository:
```bash
$ git clone git@github.com:ljbuturovic/alpaca.git
$ cd alpaca
```

2. Create a virtual environment:
```bash
$ python3 -m venv venv
$ source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
$ pip install -r requirements.txt
```

## Usage

The tool requires API keys set as environment variables:
- `OPENAI_API_KEY` for OpenAI
- `GOOGLE_API_KEY` for Google Gemini API, or `GOOGLE_CLOUD_PROJECT` for Vertex AI API
- `ANTHROPIC_API_KEY` for Anthropic
- `XAI_API_KEY` for xAI

### Examples

List OpenAI models:
```bash
$ ./llm_models.py --provider OpenAI
Listing available OpenAI models...
================================================================================
Model: babbage-002
Model: chatgpt-4o-latest
Model: codex-mini-latest
Model: dall-e-2
Model: dall-e-3
Model: davinci-002
Model: gpt-3.5-turbo
...
```

List Google models using Gemini API:
```bash
$ ./llm_models.py --provider GoogleAI
```

List Google models using Vertex AI API (with regional endpoint):
```bash
$ ./llm_models.py --provider VertexAI --region us-central1
```

List Anthropic models:
```bash
$ ./llm_models.py --provider Anthropic
Listing available Anthropic models...
================================================================================
Known Anthropic Claude models:
Model: claude-3-5-sonnet-20241022
Model: claude-3-5-sonnet-20240620
Model: claude-3-opus-20240229
Model: claude-3-sonnet-20240229
Model: claude-3-haiku-20240307
Model: claude-2.1
Model: claude-2.0

Note: Anthropic does not provide a models API endpoint.
This is a list of known models. Check https://docs.anthropic.com/en/docs/models-overview for the latest.
```

List xAI models:
```bash
$ ./llm_models.py --provider xAI
Listing available xAI models (NOTE: xAI uses aliases, so grok-4 is an acceptable API name, resolving to grok-4-0709 as of Nov. 2025)...
================================================================================
Model: grok-2-1212
Model: grok-2-vision-1212
Model: grok-3
Model: grok-3-mini
Model: grok-4-0709
Model: grok-4-1-fast-non-reasoning
Model: grok-4-1-fast-reasoning
Model: grok-4-fast-non-reasoning
Model: grok-4-fast-reasoning
Model: grok-code-fast-1
Model: grok-2-image-1212

```

## Requirements

- Python 3.7+
- See `requirements.txt` for package dependencies
- tested on Ubuntu 24.04

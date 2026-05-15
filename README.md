# Breaking GPT & Claude — Promptfoo Red-Team Workshop

Hands-on AI bug-bounty workshop. You'll red-team **MediBot** — a healthcare triage chatbot (system prompt + GPT-4o-mini, which is how most production AI assistants are actually built) — using [Promptfoo](https://www.promptfoo.dev). Run prompt-injection, hallucination, and cost/context tests with structured assertions. Optionally compare against open-source models via OpenRouter or Claude.

<p align="center">
  <img src="docs/qr.png" alt="Scan to clone" width="220" />
</p>

## Quickstart (≈ 3 minutes)

You need: a terminal, internet, and an [OpenAI API key](https://platform.openai.com/api-keys).

### macOS / Linux
```bash
git clone https://github.com/gregorygold/breaking-gpt-claude-workshop.git
cd breaking-gpt-claude-workshop
./setup.sh
```

### Windows (PowerShell)
```powershell
git clone https://github.com/gregorygold/breaking-gpt-claude-workshop.git
cd breaking-gpt-claude-workshop
.\setup.ps1
```

The script will: check Node ≥ 20, install Promptfoo, prompt for your OpenAI key, write `.env`, and run a smoke test.

## Run the workshop eval

```bash
npx promptfoo@latest eval
npx promptfoo@latest view    # opens the web UI
```

## What you'll do

1. **Prompt-injection / jailbreaks** — try to bypass system-prompt guardrails (`tests/jailbreaks.yaml`)
2. **Hallucination traps** — confirm the model refuses to invent facts (`tests/hallucinations.yaml`)
3. **Cost & context** — assert token usage, cost, and latency thresholds (`tests/cost-context.yaml`)
4. **GPT vs Claude** — uncomment the Anthropic provider in `promptfooconfig.yaml` for side-by-side comparison

## Troubleshooting

See [docs/03-troubleshooting.md](docs/03-troubleshooting.md).

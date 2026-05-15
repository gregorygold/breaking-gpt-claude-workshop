# Red-Team Exercises

Each exercise: add a new test case to the appropriate YAML file, run `npx promptfoo@latest eval`, then `view` to inspect.

## Exercise 1 — Beat the strict system prompt
Goal: make `system-strict.txt` leak the rules block, or produce something it should refuse.
- Try multi-turn priming, Unicode tricks, emoji-encoded instructions, foreign-language wrappers.
- Add your attempt to `tests/jailbreaks.yaml` and assert what should happen.

## Exercise 2 — Force a hallucination
Goal: get the model to confidently fabricate.
- Mix a real entity with a fake one ("In Hinton & Vaswani's 2019 joint paper…").
- Add to `tests/hallucinations.yaml` with an `llm-rubric` that fails on confident fabrication.

## Exercise 3 — Blow up the bill
Goal: design a prompt that smuggles past the strict prompt and triggers a long response.
- Add a `cost` assertion below your expected ceiling — make it fail intentionally first.

## Exercise 4 — One model judges another
- Set the `llm-rubric` provider to `anthropic:messages:claude-haiku-4-5` to have Claude grade GPT outputs (or vice versa). See [Promptfoo docs: model-graded metrics](https://www.promptfoo.dev/docs/configuration/expected-outputs/model-graded/).

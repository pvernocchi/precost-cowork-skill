# Contributing

Thanks for your interest in improving `precost-cowork-skill`.

This repository contains a Microsoft Copilot Cowork skill package for `/precost`. Contributions are welcome for bug fixes, documentation improvements, and refinements to the cost/value estimation logic.

## How to contribute

You can contribute by:

- Reporting bugs or unclear behavior
- Suggesting improvements to the cost estimation logic
- Updating the documentation and installation guidance
- Improving the skill packaging or release quality
- Proposing better examples and usage guidance

Before opening a pull request, please check whether an issue already exists for the topic.

## Project structure

- `README.md` — overview, usage, and repository description
- `INSTALL.md` — installation and troubleshooting guidance for uploading the skill
- `precost/SKILL.md` — the Copilot skill instructions and workflow
- `precost/references/` — pricing, routing, and card templates used by the skill
- `LICENSE` — project license

## Development workflow

1. Fork the repository and clone your fork.
2. Create a feature branch.
3. Make the change in the relevant files.
4. Validate the change by checking the affected behavior.
5. Update documentation when behavior, installation steps, or usage instructions change.
6. Open a pull request with a clear description of the problem and the fix.

## Working on the skill

This project is a skill package rather than a traditional application. When making changes, keep in mind:

- `precost/SKILL.md` is the operational source of truth for the skill workflow.
- Reference files under `precost/references/` should stay consistent with any logic changes.
- Any user-facing changes should be reflected in `README.md` and `INSTALL.md` when relevant.
- The ZIP/package form used for Cowork should still match the expected archive structure: `SKILL.md` at the archive root.

## Validation checklist

Before submitting a pull request, confirm the following:

- The skill still matches the expected Cowork archive structure.
- The `precost` folder includes the required files and references.
- Documentation still matches the current installation and usage flow.
- The change does not introduce unsupported or misleading guidance.
- Any pricing or cost logic changes are explained clearly in the PR description.

For packaging validation, ensure the archive contains `SKILL.md` at the root and that the generated ZIP matches the expected installable skill layout.

## Pull request expectations

Please keep PRs focused and easy to review:

- One topic or fix per pull request when possible
- A clear title and summary
- Mention any affected files or behavior
- Include screenshots or examples when the change affects UI or user output
- Call out any risks, assumptions, or follow-up work

## Code and content standards

- Use clear, plain language
- Keep instructions brief and actionable
- Do not add unsupported claims or unverified pricing information
- Preserve the advisory nature of the skill; it should not present estimates as guaranteed billing
- Keep examples and prompts aligned with the actual skill behavior

## Questions

If you are unsure whether a change fits the project, open a discussion or issue first. We are happy to help refine the idea before you begin.

Thank you for helping improve the project.

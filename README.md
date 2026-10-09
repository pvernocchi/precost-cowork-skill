# 💸 /precost

### Know the likely cost. Understand the potential value. Then decide.

An advisory cost-and-value pre-check for **Microsoft Copilot Cowork** tasks.
It estimates a credit range, highlights ways to run leaner, and helps you choose
whether to proceed in Cowork or use a lighter Copilot option.

[![Cowork skill](https://img.shields.io/badge/Microsoft-Copilot%20Cowork-5B5FC7?logo=microsoft&logoColor=white)](https://www.microsoft.com/microsoft-365/copilot)
[![Cowork skill](https://img.shields.io/badge/Microsoft-Cowork%20PAYG%20Consumption-5B5FC7?logo=microsoft&logoColor=white)](https://www.microsoft.com/microsoft-365/copilot)
[![Markdown](https://img.shields.io/badge/docs-Markdown-083FA1?logo=markdown&logoColor=white)](https://www.markdownguide.org/)
[![Fork of Fepilot/cowork-precost-skill](https://img.shields.io/badge/fork-Fepilot%2Fcowork--precost--skill-181717?logo=github&logoColor=white)](https://github.com/Fepilot/cowork-precost-skill)

</div>

---

## ✨ What it does

`/precost` provides a quick, transparent estimate before the substantive
work begins. It considers the task, active model, context, tools, and attachments
to show:

- 🪶 **Task size:** Light, Medium, or Heavy
- 🧮 **Estimated usage:** a range of Copilot Credits and an approximate USD
  equivalent
- ⏱️ **Potential return:** indicative time saved and value
- 🌿 **Ways to run leaner:** relevant suggestions such as narrowing scope,
  simplifying attachments, or right-sizing the model
- 🧭 **A next step:** proceed in Cowork, use a more sustainable approach, or
  switch to Copilot Chat / Microsoft 365 Copilot when appropriate

The estimate is presented as an inline Adaptive Card, followed by a choice about
how to continue.

## 🚀 Use it

Download the `precost` [latest release](https://github.com/pvernocchi/precost-cowork-skill/releases/) .zip file.
Install the file from Cowork as a Cowork skill, keeping the current file and folder structure. Invoke it with **`/precost`** or phrases such as:

- “Estimate this task”
- “What will this cost?”
- “Pre-check first”
- “Is this worth running in Cowork?”

It does not repeat the check for follow-ups or refinements in a task already in progress.

## 🔍 How the estimate works

1. It uses the task request and lightweight local context to assess the active
   model, context size, expected runtime, tools, and attachments.
2. It classifies the task as Light, Medium, or Heavy.
3. It adjusts the credit band for the model and, where appropriate, moves the
   task up or down by one class for heavy inputs, expensive tools, or a trivial
   read.
4. It estimates time saved and potential value, then presents any applicable
   sustainability suggestions.
5. It shows the estimate and asks how you want to proceed.

The estimate is a **planning range, not a bill or guarantee**. Actual usage
depends on what Cowork runs; check `/cost` and the Cost Management dashboard for
metered usage. The pre-check is advisory and does not enforce a spending limit.
Running the check itself uses a small amount of credits.

## 🗂️ Repository contents

| File | Purpose |
| --- | --- |
| [`SKILL.md`](SKILL.md) | Main workflow, invocation guidance, and guardrails |
| [`/references/pricing-reference.md`](pricing-reference.md) | Pricing context, planning bands, model multipliers, and attachment guidance |
| [`/references/value-and-routing.md`](value-and-routing.md) | Time-saved/value estimates, verdicts, and Copilot routing |
| [`/references/card-template.md`](card-template.md) | Adaptive Card structure and required disclaimer |

## 🛡️ Designed to stay lightweight

- Uses only the task prompt, session context, attachment listing, and local
  reference files for its estimate.
- Does **not** search email, calendars, the web, or file contents to calculate
  the pre-check.
- Keeps figures as ranges and identifies planning assumptions; it does not
  claim to predict the final metered charge.
- Treats the result as guidance—not a budget, hard cap, or spend control.

## 🌱 About this fork

This repository is a fork of
[**Fepilot/cowork-precost-skill**](https://github.com/Fepilot/cowork-precost-skill).

## 📝 Disclaimer

This is a community skill, not an official Microsoft product, and it comes with no warranty. It's a guidance aid — not a billing or spending control. Microsoft product names, capabilities, license entitlements, and Cowork consumption are subject to change, so verify the current details for your tenant against official Microsoft documentation, and confirm your organization's licensing before relying on any routing recommendation.

</div>

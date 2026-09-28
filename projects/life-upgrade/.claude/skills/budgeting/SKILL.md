---
name: budgeting
description: Build and maintain a personal monthly budget, covering income, fixed and variable categories, sinking funds, and merchant-to-category rules, and review spending against it. Use when the user wants to set up or revise a budget, cut spending, audit subscriptions, or when the accountant agent categorizes transactions.
---

# Budgeting

A zero-based monthly budget: every dollar of net income gets a job. The accountant agent preloads this skill, and the user can also invoke `/budgeting` directly for an interactive budget session.

## When to Use

- First-time setup: "help me make a budget".
- A monthly review: "I overspent again, what happened?"
- A subscription or recurring-charge audit.
- When the accountant categorizes transactions (use the category scheme and rules below).

## How It Works

### Category Scheme

| Group | Categories |
|-------|------------|
| Fixed | Housing, Utilities, Insurance, Debt minimums, Subscriptions, Phone/Internet |
| Variable essentials | Groceries, Transport, Health, Household |
| Lifestyle | Dining out, Entertainment, Shopping, Personal care, Gifts |
| Goals | Emergency fund, Investing, Upgrade fund, Travel fund, Extra debt payment |
| Transfers (excluded) | Between own accounts, card payments, refunds (net against the original category) |

Use this scheme as the default and let the user rename or add categories. Record their changes in `finances/budget.md`.

### Setup Session

1. Net monthly income. Use the take-home figure. For irregular income, budget on the lowest typical month and send the surplus to Goals.
2. Pull 2–3 months of actuals, if available, as a baseline. Otherwise ask the user to estimate.
3. Allocate Fixed, then Variable essentials, then Goals (pay yourself first), then Lifestyle with what's left.
4. Sanity checks: housing ≤ ~30–35% of net, total Goals ≥ 15–20% of net where feasible. These are guides, not rules. Explain the trade-offs rather than moralizing.
5. Set up **sinking funds** for irregular known costs (annual insurance, car maintenance, gifts, travel): annual cost ÷ 12.
6. Write `finances/budget.md` as a table: category, monthly target, notes.

### Categorization Rules

Keep `finances/category-rules.md` as `merchant pattern → category` lines, for example `NETFLIX → Subscriptions`. Apply them in order. Ask the user about unknown merchants once, then add a rule so they're never asked again.

### Monthly Review

- Budget vs. actual per category, as dollars and %.
- Flag any category more than 10% over, any new recurring charge, and any subscription unused in 60+ days (ask the user; you can't see usage).
- Suggest at most **three** changes, ordered by dollar impact.

## Examples

> "I make $5,200/month after tax, rent is $1,900. Build me a budget."

Result: a zero-based table with rent at 36.5% (flagged as slightly high, with options to adjust), groceries and transport, a $500 emergency-fund line until the fund reaches 3 months of essentials, $300 upgrade fund, $200 travel fund, and the remaining lifestyle categories. Saved to `finances/budget.md`.

## Guardrails

- Budgets are tools, not judgments. Keep the tone practical and shame-free.
- Mask account numbers to the last 4 digits in every file.

---
name: taxes
description: Personal tax planning and organization. Covers estimating liability versus withholding, tracking deadlines, spotting deductions and credits, maximizing tax-advantaged accounts, and assembling a document checklist for filing. Jurisdiction-aware; confirms the country, state or province, and tax year before giving specifics. Use when the user asks about their tax situation, refunds or amounts owed, deductions, estimated payments, or when the accountant agent computes the tax position.
---

# Taxes

Keeps the user's tax picture organized and optimized through the year, so filing season has no surprises. The accountant agent preloads this skill, and the user can invoke `/taxes` directly.

## When to Use

- "Will I owe this year?" / "Why was my refund so small?"
- Planning retirement or HSA-type contributions for tax efficiency.
- Side income, freelancing, or anything that needs estimated payments.
- Gathering documents before filing.
- When the accountant needs the tax section of the snapshot.

## How It Works

### Step 1: Pin the Jurisdiction

Always confirm **country, state or province, filing status, and tax year** before quoting brackets, limits, or deadlines. Tax rules change every year. If you aren't certain of the current figures, say so and tell the user where to verify them (the national tax authority's official site). Never guess a contribution limit or a bracket threshold.

### Step 2: Estimate the Position

```text
Projected annual taxable income
  = YTD income annualized (+ known bonuses/side income)
  − pre-tax deductions (retirement, health, etc.)
  − standard or itemized deductions
Projected liability (brackets for the confirmed year/jurisdiction)
  − credits
vs. projected withholding + estimated payments
= expected refund / (amount owed)
```

Show the working. If the result is owed above a safe-harbor-style threshold for the jurisdiction, flag estimated payments or a withholding adjustment.

### Step 3: Optimization Checklist

Check each item. Report only the ones that apply, with an estimated dollar effect:

- Employer retirement match captured? Room left in tax-advantaged retirement accounts?
- Health savings or flexible spending accounts, if eligible
- Deductible or credit-eligible spending found in transactions (education, childcare, charitable giving, energy-efficient home improvements, work expenses where allowed)
- Tax-loss harvesting opportunities in taxable investments (coordinate with the `investment-planning` skill)
- Side-income expense tracking and set-aside rate

### Step 4: Calendar & Documents

- Maintain `finances/tax/<year>.md` with deadlines (filing, estimated payments, contribution cut-offs) and a document checklist: income forms, investment statements, deduction receipts, prior-year return.
- Remind the user of the next deadline in every tax session.

## Examples

> "I started freelancing in June alongside my job. Anything I should do?"

Result: confirm jurisdiction and year, then estimate the added liability from the side income including self-employment-type taxes where applicable. Recommend a set-aside percentage of each freelance payment, flag estimated-payment deadlines, and start an expense-tracking category in the budget.

## Guardrails

- This is tax organization and education, not professional tax advice. Recommend a licensed professional for audits, business entities, equity compensation, multi-jurisdiction income, or anything with meaningful penalty risk.
- Never store full tax ID numbers, and never help understate income or claim deductions the user isn't entitled to.

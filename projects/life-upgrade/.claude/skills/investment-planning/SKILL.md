---
name: investment-planning
description: Long-term personal investment planning. Covers the order of operations (emergency fund, debt, match, tax-advantaged accounts, taxable), asset allocation by horizon and risk tolerance, low-cost diversified fund selection criteria, contribution automation, rebalancing, and goal projections. Use when the user asks how much to invest, where to invest it, how to allocate, whether they're on track for a goal, or when the upgrade strategist allocates the investment share of the pool.
---

# Investment Planning

Evidence-based, boring-on-purpose investing: diversify, keep costs low, automate, and stay the course. The upgrade strategist agent preloads this skill, and the user can invoke `/investment-planning` directly.

## When to Use

- "How much should I invest each month?" / "Where should it go?"
- Choosing an asset allocation or reviewing an existing portfolio.
- Projecting whether a goal (retirement age, house deposit, sabbatical) is on track.
- Allocating the investment share of the upgrade + investment pool.

## How It Works

### Step 1: Order of Operations

Check each step before moving to the next (the accountant's snapshot usually answers these):

1. Emergency fund at target, held in cash or cash-equivalents
2. High-interest debt cleared
3. Full employer retirement match
4. Tax-advantaged accounts (confirm types and current limits for the user's jurisdiction via the `taxes` skill)
5. Taxable brokerage for the remainder and for goals that need access before retirement age

### Step 2: Match Money to Horizon

| Horizon | Suggested home |
|---------|----------------|
| < 2 years (e.g. travel, upgrades, house deposit soon) | Cash / high-yield savings / short-term government bonds. **Not stocks.** |
| 2–7 years | Balanced mix, with the bond share rising as the date nears |
| 7+ years (retirement, long-term wealth) | Equity-heavy, globally diversified |

### Step 3: Allocation

- Start from horizon, then adjust for risk tolerance. Ask how the user would react to a 30–40% drop, and believe their answer.
- Build from broad, low-cost index funds (total market or global equity plus investment-grade bonds). Selection criteria: expense ratio, breadth of diversification, tracking, and tax efficiency in taxable accounts.
- Describe **fund types and criteria**, not specific tickers, unless the user asks. If they do, give examples labeled as examples, and include the criteria so they can compare alternatives.

### Step 4: Projection

Future value with monthly contributions at a conservative **real** return assumption (e.g. 4–5% for equity-heavy portfolios, lower for balanced ones). Show a range (pessimistic, base, optimistic), and say that it isn't a guarantee.

### Step 5: Automate & Maintain

- Automatic contributions scheduled right after payday.
- Rebalance annually, or when an asset class drifts more than 5 percentage points. Prefer rebalancing with new contributions to limit taxable sales.
- Log the plan in `life/investments.md`: accounts, target allocation, monthly amounts, next review date.

## Examples

> "I have $800/month for investing, I'm 29, and I want to retire by 55."

Result: confirm the emergency fund and match are in place, then fill tax-advantaged accounts first and put the remainder in taxable. Suggest roughly 90/10 global equity/bonds, adjusted to the user's drawdown answer. Project the balance at 55 across three return scenarios, compare it with a spending target, and say what monthly amount closes any gap.

## Guardrails

- Educational planning, not individualized advice from a licensed fiduciary.
- No individual stock picks, market timing, leverage, options strategies, or crypto speculation as part of the plan. If the user wants these, keep them to a small, explicitly labeled "play money" slice that is outside the plan.
- Always state assumptions (returns, inflation, fees).

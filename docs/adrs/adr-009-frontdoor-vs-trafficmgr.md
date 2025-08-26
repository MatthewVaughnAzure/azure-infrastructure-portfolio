# ADR-009 Front Door vs Traffic Manager
## Context
Global routing and WAF are required; building both is redundant for the portfolio.
## Options
1) Azure Front Door (with WAF)  
2) Traffic Manager (+ separate WAF)
## Decision
Implement **one** end-to-end (Front Door) and document trade-offs and revisit criteria.
## Consequences
Less scope, same capability for demos and DR.
## Revisit Criteria
If a target role explicitly requires Traffic Manager-only patterns, add it post-Go/No-Go.

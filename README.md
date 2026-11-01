# Wiskundehulp MCP server

Free, public, read-only MCP server with **31 maths calculators** for Dutch secondary school (vmbo, havo, vwo).
Every answer comes with **worked steps** and a link to the matching explanation page on [Wiskundehulp](https://wiskunde-hulp.com/).

- **URL (Streamable HTTP):** `https://wiskunde-hulp.com/api/mcp`
- **Auth:** none · **Cost:** free · **Data:** nothing is stored
- **Languages:** Dutch (default) and English

## Tools
| Tool | What it does |
|---|---|
| `solve_math_question` | Free-form question in Dutch or English, e.g. `los op x^2-5x+6=0`, `15% van 80`, `derivative of x^3`. Never guesses: unknown questions return suggestions. |
| `list_calculators` | All calculators with their modes and input fields. |
| `run_calculator` | Run one calculator with explicit inputs (numbers, fractions, lists, formulas). |

Topics: quadratic formula, linear equations, systems of equations, inequalities, expanding brackets, slope, formulas from tables,
percentages, fractions, ratios, scale, GCD/LCM, remainder, rounding, powers, roots, logarithms, scientific notation,
power functions, exponential growth, derivatives, Pythagoras, SOH CAH TOA, law of sines/cosines, sinusoids, area, volume,
mean/median/mode, standard deviation, normal distribution.

## Connect
**Claude (claude.ai / Desktop):** Settings → Connectors → Add custom connector → `https://wiskunde-hulp.com/api/mcp`

**Claude Code:**
```bash
claude mcp add --transport http wiskundehulp https://wiskunde-hulp.com/api/mcp
```

**Cursor / VS Code / any client with a JSON config:**
```json
{ "mcpServers": { "wiskundehulp": { "url": "https://wiskunde-hulp.com/api/mcp" } } }
```

## Example prompts
1. "Los op met stappen: 2x² − 8x + 6 = 0"
2. "What is 15% of 80? Show the steps."
3. "Bereken de afgeleide van x³ − 2x."
4. "In a triangle with a = 6, b = 5, c = 7: find angle A."
5. "Wat is de standaardafwijking van 2, 5, 5, 8, 11?"

## Example response (`solve_math_question`, "15% van 80")
```
Antwoord: 12

Stappen:
1. Formule: bedrag = getal × percentage ÷ 100
2. Invullen: 80 × 15 ÷ 100
3. Eerst het product: 80 × 15 = 1.200
4. Delen door 100: 1.200 ÷ 100 = 12

Uitleg, oefenen en de rekenmachine (Percentage berekenen): https://wiskunde-hulp.com/percentage-berekenen/
```
Dutch answers use a decimal comma (1.028 = one thousand twenty-eight); English answers use 1,028.

## Privacy
No accounts, no cookies, no storage of questions. Requests pass through standard hosting logs (Vercel).
Privacy policy: https://wiskunde-hulp.com/privacybeleid/

## Support
Contact: https://wiskunde-hulp.com/contact/

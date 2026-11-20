# Jock Taxes for Claude

Jock Taxes estimates what professional athletes in MLB, NBA, NFL and NHL actually take home after federal, state, local and "jock tax" obligations. A jock tax is the income tax that states and cities charge visiting players for the days they work there. This plugin connects Claude to the Jock Taxes calculation engine, the same one that powers [jocktaxes.com](https://jocktaxes.com), so you can ask contract and tax questions in plain language.

## What you can ask

- "What does a $12M NHL salary on the Toronto Maple Leafs take home this season?"
- "What salary on the Texas Rangers matches $30M after tax on the Los Angeles Dodgers?"
- "How much more would an NBA player keep after a move from Golden State to Miami at the same pay?"
- "Split $20M into base salary, signing bonus and performance bonus for an NFL player on the Jets."

## What the plugin includes

This plugin contains one component: a reference to the Jock Taxes remote MCP server at `https://jocktaxes.com/mcp/claude`. It has no hooks, scripts, or local code, and installs nothing on your machine.

The server provides these tools:

| Tool | Purpose |
| - | - |
| `calculate_{mlb,nba,nfl,nhl}_tax` | Tax and take-home estimate for one season on one team |
| `equivalent_{mlb,nba,nfl,nhl}_salary` | Gross salary on another team that matches a known after-tax income |
| `player_movement_{mlb,nba,nfl,nhl}` | Take-home change when a player moves teams at the same gross pay |
| `list_team_players` | Player ids and pay for one team and season from public salary tables |
| `list_tax_calculator_inputs` | Leagues, seasons, filing statuses and team codes the calculators accept |
| `get_profile` | Returns the Jock Taxes account linked to the request, if any |

## Data sent and usage limits

When Claude calls a tool, it sends the calculation inputs over HTTPS to jocktaxes.com. Those inputs are league, team, season, salary or pay split, filing status and domicile. The plugin doesn't read your files, environment variables or credentials, and it doesn't send data anywhere else. Jock Taxes counts calculations to enforce a free monthly quota. When the quota runs out, the tool result links to a Jock Taxes Pro account page, where free and paid plans are available. See the [Jock Taxes privacy policy](https://jocktaxes.com/privacy/) for how request data is handled.

## Disclaimer

Results are calculated estimates for information and comparison. They are not tax, legal or financial advice.

## Support

Email brandon@jocktaxes.com or visit [jocktaxes.com](https://jocktaxes.com).

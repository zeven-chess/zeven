# Zeven

**A free, open-source chess improvement platform.**

Enter a Chess.com username, and Zeven studies your recent games, finds where
you are losing rating points, and builds a personalised improvement report.
No subscription, no paywall, no locked features.

> **Status: planning.** Nothing described below is implemented yet. This
> README describes the intended product. See [Roadmap](#roadmap) for progress.

## Principles

- Free forever: no subscriptions, premium tiers or paid analysis
- Open source: all code is public, and contributions are welcome
- Transparent methodology: every score is explained and reproducible
- Self-hostable: runs on your own machine
- Privacy first: public usernames only, and no unnecessary personal data
- Honest analysis: no invented statistics, no fabricated game examples

## Planned features

- **Game retrieval:** your recent games from the public Chess.com data
- **Game analysis:** Stockfish-based evaluation of mistakes, in context
- **Rating leaks:** the rating points you lost in games decided by each cause
  (tactical blunders, openings, time trouble, failed conversion, and so on),
  with every example traced to a real game
- **Chess DNA:** a five-axis profile compared with players at your level
- **Opening analysis:** results, where your preparation ends, and clock use
- **Interactive review:** a board with your move, the engine's move and the
  best continuation
- **Puzzles from your own blunders**
- **Personalised training plan and rating projection** under clearly stated
  assumptions

## How it works (intended)

Zeven fetches your games, evaluates every position with Stockfish, finds the
decisive moment in each lost game, classifies its cause, and aggregates
patterns across games. It reports measured facts (rating points lost,
frequency, evaluation swings) separately from modelled estimates, and shows
sample sizes and uncertainty. The methodology will be documented in
`docs/methodology/` and versioned.

## Roadmap

| Phase | Focus | Status |
|---|---|---|
| 0 | Research and planning | In progress |
| 1 | Repository and foundations | In progress |
| 2 | Chess.com integration | Not started |
| 3 | Engine integration | Not started |
| 4 | Leak detection | Not started |
| 5 | Reports and interactive board | Not started |
| 6 | Training plans and puzzles | Not started |
| 7 | Progress tracking | Not started |
| 8 | Public launch | Not started |

## Documentation

- Architecture decisions: [`docs/adr/`](docs/adr/)

## Contributing

Contributions are welcome once the foundations are in place. A
`CONTRIBUTING.md` guide is coming soon. For now, feel free to open an issue
to discuss ideas.

## Security

Please do not report vulnerabilities in public issues. Use GitHub's private
vulnerability reporting (Security tab). Read `SECURITY.md` for more info.

## Licence

Licensed under the [GNU Affero General Public License v3.0](LICENSE). Third-party
components keep their own licences.

## Disclaimer

Zeven is an independent project. It is not affiliated with, endorsed by or
sponsored by Chess.com, Lichess or any other chess analysis websites. Those names belong to their
respective owners and are used only to describe compatibility or comparison.

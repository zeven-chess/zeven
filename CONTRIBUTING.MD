# Contributing to Zeven

Thank you for your interest. Zeven is a free, open-source project, and
contributions of all kinds are welcome: code, documentation, bug reports,
methodology review and ideas.

## Project status

Zeven is in the planning and foundations stage. Development setup
instructions will be added once the project skeleton exists. Until then, the
most useful contributions are discussion, feedback on the architecture
decisions in `docs/adr/`, and review of the methodology as it is documented.

## Before you start

- For anything beyond a small fix, open an issue first so we can agree on the
  approach before you spend time on it.
- Changes to scoring or analysis methodology need an Architecture Decision
  Record (ADR) in `docs/adr/`, because they affect every report.
- Check the [Code of Conduct](CODE_OF_CONDUCT.md). By taking part, you agree
  to follow it.

## Making a change

1. Fork the repository and create a branch from `main`.
2. Make your change, with tests where it makes sense.
3. Open a pull request and fill in the template.
4. Automated checks must pass, and a maintainer will review.

Once CI exists, it will run linting, type checks and tests on every pull
request. We aim to keep checks fast, and to explain any failure clearly.

## Contribution rules

- Every statistic and example shown to users must trace back to real data.
  Never fabricate game examples or invent figures.
- Do not copy code, assets or branding from proprietary products.
- Only add a dependency if it is justified, and check its licence is
  compatible with AGPL-3.0.
- By contributing, you agree that your work is licensed under the project's
  licence (AGPL-3.0-or-later).
- AI-assisted code is welcome, provided you understand it, can explain it if
  asked, and have tested it. You remain responsible for its correctness and
  its licensing: do not submit generated code that copies from
  incompatible or proprietary sources.

## Questions

Open an issue or a discussion. There are no silly questions.
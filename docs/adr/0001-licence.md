# ADR-0001: Project licence

- Status: Proposed
- Date: 2026-11-06

## Context

Zeven is a free, open-source chess improvement platform. The project
must stay free for users and community-owned, and it may later be run as a
public website. Our planned dependencies include Stockfish (GPL-3.0),
python-chess (GPL-3.0+) and possibly chessground (GPL-3.0). Combining our
code with GPL-licensed libraries means the combined work must be distributed
under a GPL-compatible licence.

## Decision

License the project under **AGPL-3.0-or-later**.

## Alternatives considered

- **MIT / Apache-2.0:** permissive and popular, but incompatible with
  distributing a combined work that includes GPL-3.0 dependencies.
- **GPL-3.0:** compatible, but allows someone to run a modified, closed
  version as a hosted service without sharing their changes.

## Consequences

- Modified versions that are run as a network service must offer their source
  to users, which protects the "free forever, for the people" principle.
- Some companies avoid AGPL software. We accept that.
- Every dependency must be checked for compatibility. We will add a licence
  check to CI and maintain a NOTICE file for third-party licences.
- Documentation and data files may use a separate licence (to be decided).
- This is not legal advice. Consider a legal review before public launch.
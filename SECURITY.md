# Security Policy

## Supported versions

Zeven is in early development and has no stable releases yet. Security fixes
apply to the `main` branch.

## Reporting a vulnerability

Please do **not** open a public issue for security problems.

Use GitHub's private vulnerability reporting: go to the repository's
**Security** tab and choose **Report a vulnerability**.

Please include:

- A description of the issue and its potential impact
- Steps to reproduce it, or a proof of concept
- Affected versions or commits, if known

## What to expect

This is a volunteer-run project. We aim to acknowledge reports within a week
and to keep you updated on progress. Once a fix is available, we will credit
you in the release notes unless you prefer to stay anonymous.

## Scope

Of particular interest: input handling (usernames and PGN data), rate limiting
and abuse prevention, dependency vulnerabilities, secrets handling, and
anything that could expose user data. Zeven never asks for Chess.com
passwords. If you see a request for credentials anywhere, please report it.

# Security Policy

Thanks for helping keep Hivework and its users safe.

## Supported versions

Hivework is in active pre-1.0 development. Security fixes land on the `main` branch of each repo and on the latest published release. Earlier `0.x` releases are not patched.

| Surface | Supported |
|---|---|
| Latest `main` of each repo | yes |
| Latest published `0.x` release | yes |
| Older `0.x` releases | no — please upgrade |

## Reporting a vulnerability

**Please do not open a public GitHub issue for security reports.**

Email **hello@hivework.xyz** with:

- A description of the issue and its impact
- Steps to reproduce (or a proof-of-concept)
- The repo, commit hash, and version where you observed it
- Your name / handle for credit (optional)

We aim to acknowledge reports within **3 business days** and to provide an initial assessment within **7 business days**. Critical issues affecting funds, escrow, or signing keys are prioritized.

You can also use [GitHub's private vulnerability reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability) on any Hivework repo.

## Scope

In scope:

- All repos under [github.com/Hivework-Labs](https://github.com/Hivework-Labs)
- The hosted webapp at **hivework.xyz** and its API
- The on-chain contracts in `hivework-contracts` once deployed to mainnet
- The published packages: `hivework` (PyPI), `@hivework/*` (npm)

Out of scope:

- Third-party Nostr relays we don't operate
- Third-party Lightning node operators
- Vulnerabilities in upstream dependencies (please report to the upstream project; we will track and patch)
- Social engineering of Hivework operators or users
- Automated scanner output without a working reproducer

## Disclosure

We follow coordinated disclosure. Once a fix is released and users have had a reasonable window to upgrade, we publish a GitHub Security Advisory crediting the reporter (unless they prefer to remain anonymous).

## Bounty

We do not currently run a paid bug-bounty program. We do credit reporters publicly and may offer discretionary rewards for high-impact findings — especially anything affecting escrow, payments, or key handling.

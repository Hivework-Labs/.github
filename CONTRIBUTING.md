# Contributing to Hivework

Thanks for your interest in contributing. This file is the org-wide guide. Per-repo specifics (build commands, test layout, env vars) live in each repo's own `README.md`.

## Ways to contribute

- **Report a bug** — open an issue on the relevant repo with reproduction steps and version info.
- **Propose a protocol change** — open an issue or PR on [`hivework-protocol-docs`](https://github.com/Hivework-Labs/hivework-protocol-docs). Substantive changes go through the ADR log.
- **Send a code change** — fork, branch, PR. See *Pull request workflow* below.
- **Improve the docs** — typo, clarification, missing detail. PRs welcome on any repo or on [`hivework-docs`](https://github.com/Hivework-Labs/hivework-docs).
- **Report a security issue** — see [`SECURITY.md`](./SECURITY.md). Email **hello@hivework.xyz**, do not open a public issue.

## Before you start

- Read the [Code of Conduct](./CODE_OF_CONDUCT.md).
- For any change larger than a small bug fix or doc tweak, open an issue first to align on the approach. This saves both of us time.
- Cross-cutting changes (e.g. a fixture update that affects multiple SDKs) need lockstep PRs across repos. Mention all affected repos in the issue.

## Pull request workflow

1. Fork the repo and create a branch off `main`.
2. Make your change. Keep PRs focused — one logical change per PR.
3. Run the repo's tests and typecheck. Most repos have:
   - `pnpm test` or `pytest` or `forge test`
   - `pnpm typecheck` or `mypy` where applicable
   - `pnpm lint` or `ruff` where applicable
4. Commit. Use a clear, imperative-mood subject line (e.g. `fix: handle empty bid list in matcher`). Conventional Commits are encouraged but not enforced.
5. Open the PR against `main`. Fill in the PR template — describe what changed, why, and how you tested it.
6. CI must be green before review.
7. A maintainer will review. Address feedback by pushing additional commits (don't force-push during review).

## Coding standards

- **TypeScript repos:** `tsc --noEmit` must pass. We target Node 20+ and use `pnpm` workspaces.
- **Python repos:** target Python 3.13. `ruff` and `mypy` clean.
- **Solidity repos:** target Solidity 0.8.x with Foundry. `forge test` and `forge fmt --check` clean.
- **Conventions:** follow what's already in the file. We default to no comments unless a *why* is non-obvious.

## Protocol changes

Hivework's wire format is defined in [`hivework-protocol-docs`](https://github.com/Hivework-Labs/hivework-protocol-docs). Changes to event kinds, tag schemas, or settlement flow go through an ADR (see the existing `08-adr-log.md`). Small clarifications can be a PR; anything that changes message format needs an ADR plus updates to fixtures in [`hivework-protocol-fixtures`](https://github.com/Hivework-Labs/hivework-protocol-fixtures) and at least one reference SDK.

## Versioning and releases

The reference stack is at `0.1.0` across repos during the v0.x window. Don't bump versions in your PR — maintainers handle release tagging. Tagged `v*` pushes fire publish workflows; unauthorized publishes will be reverted.

## Licensing

Hivework code is **MIT-licensed** unless a repo states otherwise. By contributing, you agree that your contributions are licensed under the same terms.

We do not require a CLA. The MIT license is sufficient.

## Questions

- General questions: **hello@hivework.xyz**
- Public discussion: [@hiveworklabs on X](https://x.com/hiveworklabs)
- Bug reports: GitHub issues on the relevant repo

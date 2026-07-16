# Contributing

Thanks for taking a look. Before opening anything, a quick note on scope.

This repository is a personal documentation kit, shared publicly in case any of it is useful to others running a security or GRC function. It is not a community-maintained project. Issues and pull requests are welcome, but responses are best-effort, and changes that don't fit the kit's scope may be declined even when they're objectively good ideas. If that's not what you're after, fork freely; CC BY 4.0 is permissive on purpose.

The principles in the [README](../README.md) apply here too:

- Organised by altitude and sponsorship, not topic.
- Vendor-neutral. Nothing here describes a specific organisation, tenant, or product configuration.
- Generic without being hollowed out. If a change strips a template down to something unusable, it's the wrong change.

## Reporting issues

Good issues are specific. Please include:

- Which file, and which section.
- What's wrong: factually incorrect, badly scoped, contradicts another artefact in the kit, or just unclear.
- What you'd expect instead.

For new template requests, describe the operational problem the template would solve, not just its title. That's what makes the request assessable.

## Security issues

Don't open a public issue for anything that looks like it would lead a reader to do something insecure if followed as written. See [SECURITY.md](SECURITY.md).

## Proposing changes

Before you spend real time on a new artefact, open an issue to sketch the idea and where it fits in the layer model. That avoids both of us discovering, at PR review, that it doesn't fit.

For small fixes (typos, broken links, factual corrections), a PR straight to `main` is fine.

When you open a PR:

- Keep it focused on one artefact or one fix.
- The description should say what changed and why.
- If you're adding a template, state which layer it belongs to and what real-world discipline it's modelled on (without naming a specific organisation).
- Confirm there's no vendor-specific, tenant-specific, or otherwise non-generic content in what you're adding.

By submitting a contribution you agree it can be released under the project's [CC BY 4.0 licence](../LICENSE) (or, for bundled code, its stated software licence).

## Style

- Australian English (organise, licence-the-noun).
- Numbers over adjectives: a claim with a figure states the figure.
- When you write or adapt a Standard, make the must/should/may verb split explicit; a Standard that blurs mandatory and recommended isn't doing its job.
- Consistent front matter on `security-docs-kit` and `soc2-kit` artefacts: type, owner role, version, review cadence.

## Commits and branches

- Write commit messages as commands: "Add X", "Fix Y".
- One logical change per commit where practical.
- Branch from `main`. Feature branches named however you like; they'll be deleted on merge.

## Code of conduct

See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

## Questions

If you're not sure whether something belongs here or in the companion [ITSM kit](https://github.com/benguin5611/ITSM/tree/main/docs-kit), open an issue and ask before writing anything. That's nearly always faster than guessing: the split is by audience (solo IT operator vs. security/GRC practitioner), not by topic, and it isn't always obvious from a title alone.

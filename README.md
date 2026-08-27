# foreground-guard

**This repository is archived and read-only. foreground-guard now ships from
[karlkfi/claude-bouncer](https://github.com/karlkfi/claude-bouncer).**

```
/plugin marketplace add karlkfi/claude-bouncer
/plugin install foreground-guard@claude-bouncer
```

Those two lines replace the pair this repo used to document. The plugin itself
did not change — same hook, same `.claude/foreground-guard.json`, same
`FOREGROUND_GUARD_OVERRIDE=<reason>` prefix, same
`/foreground-guard:friction-report`. Nothing in your own repo needs editing.

The five guards — `workspace-guard`, `branch-guard`, `prod-guard`,
`exit-status-guard`, `foreground-guard` — all parse the same Bash command
strings, and were re-implementing that parser five times over. They share one
now, so they share a repository, a test suite, and a release pipeline.

## Where the docs went

[`plugins/foreground-guard`](https://github.com/karlkfi/claude-bouncer/tree/main/plugins/foreground-guard)
in claude-bouncer: decision table, covered forms, exemptions, config reference,
friction report.

Read that rather than anything in this repo. The last release here was `v0.5.1`
and the copy in claude-bouncer is ahead of it, so the pages under `docs/` here
describe behavior the shipping plugin no longer has.

## Switching an existing install

The marketplace name changes from `foreground-guard` to `claude-bouncer`, so an
existing install has to be removed and re-added — an update will not cross that
boundary, and the old marketplace still clones fine, so nothing tells you it has
gone quiet:

```
claude plugin uninstall foreground-guard@foreground-guard
claude plugin marketplace remove foreground-guard
claude plugin marketplace add karlkfi/claude-bouncer
claude plugin install foreground-guard@claude-bouncer
```

Restart Claude Code (or `/reload-plugins`) to apply. The `/plugin` menu does the
same four steps interactively, on the CLI, the IDE extensions, and Claude Code
for Claude Desktop.

**Repoint auto-update too.** If you followed the old install instructions you
have an `extraKnownMarketplaces` entry in `~/.claude/settings.json` naming this
repository, and it will go on refreshing a marketplace that will never publish
another release. Replace it:

```json
{
  "extraKnownMarketplaces": {
    "claude-bouncer": {
      "source": { "source": "git", "url": "https://github.com/karlkfi/claude-bouncer.git" },
      "autoUpdate": true
    }
  }
}
```

The four sibling guards are one `install` line each against that same
marketplace — see the
[claude-bouncer README](https://github.com/karlkfi/claude-bouncer#install).

## What is still here

History, and the links that point into it. Archiving keeps every issue, pull
request and tag resolving; it does not delete them. New issues and pull requests
belong on
[claude-bouncer](https://github.com/karlkfi/claude-bouncer/issues). The
pre-move documentation is readable at the
[`v0.5.1`](https://github.com/karlkfi/claude-foreground-guard/tree/v0.5.1) tag.

## License

[MIT](LICENSE)

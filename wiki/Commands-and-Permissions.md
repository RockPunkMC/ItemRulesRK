# Commands and permissions

## Commands

| Command | Purpose |
|---|---|
| `/itemrules gui` | Open the graphical administration panel |
| `/itemrules reload` | Safely reload configuration and rules |
| `/itemrules list [page]` | List rules |
| `/itemrules info <rule>` | Show rule details |
| `/itemrules validate <rule>` | Validate configuration |
| `/itemrules test [trigger]` | Dry-run the held item |
| `/itemrules doctor` | Show rules, hooks and diagnostics |
| `/itemrules stats` | Show runtime counters |
| `/itemrules group <group> <enable\|disable>` | Change a group runtime state |
| `/itemrules export <rule>` | Export a rule safely |
| `/itemrules import <file>` | Import as disabled private drafts |
| `/itemrules history <rule>` | List stored revisions |
| `/itemrules exception <player> <rule\|*> <duration\|permanent\|clear>` | Manage temporary exceptions |

Alias: `/irules`.

## Permission model

`itemrules.admin` grants every administrative permission and defaults to server operators. Being OP does **not** bypass gameplay rules unless `bypass.op: true` is explicitly configured.

Common nodes:

- `itemrules.gui.open`, `itemrules.gui.view`
- `itemrules.gui.create`, `.edit`, `.rename`, `.apply`, `.toggle`, `.duplicate`
- `itemrules.gui.archive`, `.restore`, `.delete`, `.purge`
- `itemrules.gui.history`, `.history.restore`
- `itemrules.gui.groups.view`, `.groups.edit`, `.groups.toggle`
- `itemrules.gui.drafts.view-own`, `.view-all`, `.discard-own`, `.discard-all`
- `itemrules.gui.import`, `.export`, `.templates`
- `itemrules.gui.exceptions.view`, `.grant`, `.revoke`
- `itemrules.gui.actions.console`, `.player`, `.destructive`, `.placeholders`
- `itemrules.reload`, `.list`, `.info`, `.test`, `.doctor`, `.stats`, `.group`
- `itemrules.export`, `.import`, `.exception`, `.validate`, `.history`, `.draft`

All permissions are rechecked server-side when the operation executes. Hiding a button or command is never the security boundary.

## Rule bypass

Rules do not require a permission to apply. `bypass-permission: ""` means nobody bypasses that rule. To add an explicit bypass:

```yaml
bypass-permission: "myserver.itemrules.pearl.bypass"
```

Grant that node only to players who should ignore that specific rule.


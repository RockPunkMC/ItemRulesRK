# Visual rule editor

Open the editor with:

```text
/itemrules gui
```

## Create a rule

1. Click **Create rule**.
2. Choose **From scratch**, **Duplicate**, **Template** or **Import**.
3. Enter a unique lowercase ID in chat, for example `spawn_pearl_block`.
4. Select or capture the item.
5. Configure triggers, scope, conditions and actions.
6. Open **Final review**.
7. Use **Dry run** to evaluate the held item without executing actions.
8. Click **Save and apply** and confirm.

Nothing affects gameplay while the rule is only a draft.

## Draft safety

- Closing the inventory does not delete progress.
- Disconnecting or restarting does not delete saved drafts.
- **Pending drafts** lets you continue later.
- Undo and redo are available during the editing session.
- Two administrators cannot silently overwrite the same rule.
- Invalid or incomplete drafts cannot be applied.

## Editor sections

| Section | What it controls |
|---|---|
| Identity | Rule ID and enabled state |
| Item and matching | Material, custom provider, name, lore, model data and enchantments |
| Triggers | Events that cause the rule to be evaluated |
| Scope | Hand, worlds, WorldGuard regions and gamemodes |
| Conditions | Health, Y, time, XP, economy, combat, permissions and placeholders |
| Actions | Cancel, messages, effects, commands, removal and damage |
| Cooldown | Duration, scope, persistence and display |
| Inventory limit | Maximum amount, matching mode and shared materials |
| Priority | Evaluation order and stop-processing |
| Groups | Optional rule-group membership |
| Permissions | Explicit bypass and permission conditions |
| Final review | Validation, conflicts, dry run and apply |

## Rule administration

**All rules** supports search, filtering, pagination and visual sorting. Visual sorting never changes gameplay priority.

GUI-managed rules can be edited, duplicated, renamed, archived, exported or moved to trash. Manual rules from `rules.yml` are read-only in the GUI; duplicate them to create an editable GUI draft without destroying comments.

## Dry run

Hold the item you want to test and open **Dry run**. It checks every configured trigger and reports matches, reasons, actions and unavailable dependencies. It never sends commands, deals damage, changes inventory, starts cooldowns, increments statistics or fires public execution events.


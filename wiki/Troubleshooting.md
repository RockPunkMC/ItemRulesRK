# Troubleshooting and recovery

## A rule does not match

1. Run `/itemrules doctor`.
2. Confirm the rule is enabled and its group is enabled.
3. Hold the exact item and use dry run.
4. Check material, hand and trigger.
5. Check world, region and gamemode spelling.
6. Verify optional dependencies are hooked.
7. Confirm the player does not have the rule's explicit bypass permission.

## The GUI says the rule is invalid

Open the rule detail or final review. Invalid rules remain visible for administration but are excluded from every gameplay index. Fix the reported field; other valid rules continue working.

## PlaceholderAPI, WorldGuard or economy is unavailable

Install a compatible dependency and restart the server. Do not use Bukkit `/reload`. `/itemrules doctor` distinguishes not installed, disabled and hook failure states.

## A draft disappeared from the open menu

Open `/itemrules gui` and select **Pending drafts**. Closing a menu or disconnecting does not delete a saved draft. A draft is removed only by explicit discard/purge or after it is safely applied according to the workflow.

## Safe mode / transaction recovery

If an interrupted multi-file transaction cannot be recovered, ItemRulesRK keeps gameplay on the last loadable snapshot and makes administrative editing read-only. Do not delete `data/transactions/` blindly. Back up the plugin folder and inspect the console plus `/itemrules doctor`.

## Update files

Files named `*.update.1.4.0.yml` show new defaults. They do not replace your existing files. Copy only the settings you want after reviewing them.

## Reporting a problem

Include:

- server software and exact Minecraft version;
- Java version;
- ItemRulesRK version;
- `/itemrules doctor` output;
- relevant rule with secrets removed;
- complete error stack trace;
- installed versions of WorldGuard, PlaceholderAPI, Vault or custom-item plugins.


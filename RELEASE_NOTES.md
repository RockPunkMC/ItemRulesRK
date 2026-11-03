# ItemRulesRK 1.0.0

Version 1.0.0 is the first public release of ItemRulesRK, combining its event-driven rule engine with a production-oriented visual editor.

## Added

- Main GUI, rule list, detail view, creation flow, templates, drafts, groups, diagnostics, statistics, exceptions, history and trash.
- Persistent isolated drafts with atomic saves, undo/redo and safe discard recovery.
- Safe editing of existing GUI rules with expiring locks and base-revision conflict checks.
- Production-loader validation before applying and transactional rollback across rules and GUI groups.
- Rule-specific dry runs with no actions, public events, cooldowns, inventory mutations or statistics.
- English and Spanish general/GUI locale files with per-key bundled fallback.
- GUI-managed rule/group files that never rewrite commented manual files.
- Safe import as disabled private drafts and sanitized export.
- Configurable retention for trash, history and the administrative audit log.
- Safe retention of completed transaction journals; interrupted journals are never expired before recovery.
- Defensive limits for rules, groups, list values, lore, messages, commands, import size and YAML depth.
- Automatic capture of material, name, lore, CustomModelData, enchantments and detected custom-item provider IDs.
- A complete enchantment criteria editor and visual rule-list ordering that never changes execution priority.
- Dry run evaluation across every configured trigger, with explicit partial results when a required hook is unavailable.
- Additional templates for world/region restrictions, cooldowns, limits, combat and consumption.

## Security and stability

- All GUI clicks and drags are cancelled server-side, including bottom-inventory transactions while an editor is open.
- Every sensitive GUI operation rechecks its granular permission at execution time.
- Console/player commands, destructive actions and PlaceholderAPI command expansion require dedicated permissions when applying.
- Manual rules and groups are read-only in the GUI.
- Invalid drafts remain isolated; malformed imports cannot change active gameplay.
- Reload is atomic and preserves the previous working snapshot when validation fails.
- No repeating player or inventory scan was added.

## Migration

- `config-version: 4`, `rules-version: 4`, `groups-version: 2`.
- Legacy `imported-rules.yml` content migrates to `gui-rules.yml` once; the original remains untouched.
- Legacy root message overrides migrate into `locale/` once; originals remain untouched.
- Missing new locale keys fall back to the bundled language without overwriting customized files.

## Verified in this workspace

- Clean Maven test/package build targeting Java 8 bytecode.
- Public YAML resources and English/Spanish key parity.
- Paper 1.16.5 startup and clean shutdown using Java 8.
- Legacy rule migration smoke test.

## Deployment-specific live checks still required

- Player-driven GUI interaction on the target production server.
- Installed WorldGuard, PlaceholderAPI, Vault economy and custom-item provider versions.
- The target server's newest Purpur build and Bedrock/Geyser client UX.
- A real bStats project ID and final update endpoint before enabling those optional services.

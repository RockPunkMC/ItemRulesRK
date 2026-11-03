# ItemRulesRK Wiki

ItemRulesRK is an event-driven item restriction engine for Spigot, Paper and Purpur. It lets server owners control where, when and how items may be used, limit inventory quantities, add cooldowns and combine rules with worlds, regions, permissions, combat, economy and placeholders.

## Start here

1. [Installation and first start](Installation.md)
2. [Create your first rule with the GUI](GUI-Guide.md)
3. [Create and edit rules in YAML](Rules-and-YAML.md)
4. [Commands and permissions](Commands-and-Permissions.md)
5. [Integrations](Integrations.md)
6. [Troubleshooting and safe updates](Troubleshooting.md)
7. [Guía rápida en español](Guia-Rapida-ES.md)

## Compatibility

- Minecraft 1.16.5 and newer Bukkit-compatible servers.
- Spigot, Paper and Purpur.
- Java 8 on Minecraft 1.16.5; newer Minecraft versions require the Java version required by that server.
- One ItemRulesRK JAR covers the supported range.
- Optional hooks: WorldGuard, PlaceholderAPI, Vault economy, ItemsAdder, Oraxen, Nexo and MMOItems.

ItemRulesRK has no repeating player or inventory scanner. Rules are evaluated only from relevant server events.

## Main files

| File | Purpose |
|---|---|
| `config.yml` | Language, safety, limits, hooks, retention and optional services |
| `rules.yml` | Manual rules; the GUI never rewrites this file |
| `groups.yml` | Manual rule groups |
| `gui.yml` | Menu presentation settings |
| `gui-rules.yml` | Rules safely published through the GUI |
| `gui-groups.yml` | Groups managed through the GUI |
| `templates.yml` | Reusable rule templates |
| `locale/` | General and GUI translations |

Never use Bukkit `/reload`. Use `/itemrules reload` after editing YAML manually.


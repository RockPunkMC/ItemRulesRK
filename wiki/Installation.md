# Installation and first start

## Requirements

- A Spigot, Paper or Purpur server running Minecraft 1.16.5 or newer.
- The Java version required by your Minecraft server.
- Permission to stop and start the server and upload plugins.

## Install

1. Stop the server completely.
2. Put `ItemRulesRK-1.0.0.jar` inside `plugins/`.
3. Start the server.
4. Check the console for `ItemRulesRK enabled` and the loaded-rule count.
5. Run `/itemrules doctor` to see loaded rules and optional hooks.
6. Run `/itemrules gui` as an administrator.

A fresh installation changes no gameplay because every bundled example is disabled.

## Select a language

In `config.yml`:

```yaml
language: "en"
language-settings:
  use-client-locale: false
  fallback: "en"
```

Use `language: "es"` for Spanish. If `use-client-locale` is true, each supported client language is selected automatically and missing keys fall back to English.

## Safe configuration reload

After changing `config.yml`, `rules.yml`, `groups.yml`, `gui.yml` or locale files, run:

```text
/itemrules reload
```

The reload is atomic: if the new rules contain a critical error, the last working snapshot remains active. Active editing sessions and drafts are not silently destroyed.

## Updating ItemRulesRK

1. Stop the server.
2. Back up `plugins/ItemRulesRK/`.
3. Replace only the JAR.
4. Start the server and read the console.

ItemRulesRK preserves customized files. When new settings are available, it creates an update file such as `config.update.1.0.0.yml` instead of replacing your configuration.


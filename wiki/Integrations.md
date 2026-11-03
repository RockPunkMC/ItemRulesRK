# Integrations

Every integration is optional. A missing dependency disables only its related features.

## WorldGuard

Used by non-empty region conditions. Region IDs are compared in lowercase. The GUI lists regions from loaded worlds when the installed WorldGuard API supports it.

## PlaceholderAPI

Used for placeholder conditions and optional placeholder expansion in actions. Command expansion is disabled by default and additionally protected by `itemrules.gui.actions.placeholders`.

Example condition concept: `%player_level% >= 10`. Configure it through the GUI to avoid YAML mistakes.

## Vault economy

Vault plus an economy provider enables minimum and maximum balance conditions. Without a working economy provider, rules requiring economy conditions are diagnosed instead of crashing the plugin.

## Custom item plugins

Supported identity hooks:

- ItemsAdder
- Oraxen
- Nexo
- MMOItems

The GUI can capture the custom identity from an item already held by the administrator. A full provider catalog appears only when a provider exposes a compatible official listing API.

## Geyser and Floodgate

ItemRulesRK does not require them. Menus avoid hidden destructive gestures and use explicit action screens where possible. Always test the GUI with a real Bedrock client because inventory presentation is controlled partly by Geyser.


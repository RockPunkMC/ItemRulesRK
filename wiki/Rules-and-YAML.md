# Rules and YAML

Use the GUI when possible. Manual YAML is useful for version control, bulk editing and advanced administration.

## Minimal rule

```yaml
rules-version: 4
rules:
  block-pearls:
    enabled: true
    priority: 100
    stop-processing: true
    hand: ANY
    item:
      material: ENDER_PEARL
    triggers:
      - RIGHT_CLICK
      - THROW
    actions:
      cancel: true
      message:
        enabled: true
        value: "<#FF5555>You cannot use Ender Pearls here."
    bypass-permission: ""
```

Empty or missing conditions mean **ANY**. Values inside one condition use OR; different condition types use AND. Use block lists for normal values and `[]` only for an intentionally empty list.

## Triggers

`RIGHT_CLICK`, `LEFT_CLICK`, `CONSUME`, `PLACE`, `DROP`, `PICKUP`, `SHOOT`, `THROW`, `BREAK`, `CRAFT`, `ENCHANT`, `SWAP_HAND`, `TOTEM_USE`.

## World restriction

```yaml
conditions:
  worlds:
    mode: WHITELIST
    values:
      - world
      - arena
```

`WHITELIST` matches listed values. `BLACKLIST` matches everything except listed values.

## WorldGuard regions

```yaml
conditions:
  regions:
    mode: WHITELIST
    values:
      - spawn
      - safezone
```

A non-empty region list requires WorldGuard. Configure `hooks.fail-closed` in `config.yml` to decide the safe behavior if WorldGuard unexpectedly fails.

## Cooldown

```yaml
cooldown:
  enabled: true
  duration: 30
  scope: RULE
  persist: false
  bypass-permission: ""
  display:
    actionbar: true
    message: "<#FFAA00>Wait <white>{time}s"
```

Scopes: `RULE`, `ITEM` or `PLAYER`. Duration is in seconds.

## Inventory limit

```yaml
inventory-limit:
  enabled: true
  maximum: 16
  count-mode: MATERIAL
  shared-materials: []
  excess-action: DENY_PICKUP
```

Count modes: `MATERIAL`, `MATCHING_ITEM`, `EXACT_STACK`. Excess actions: `DENY_PICKUP`, `DROP`, `REMOVE`.

Pickup is partial: a player holding 15 pearls can collect one from a stack and the remaining ground items stay protected.

## Custom item providers

```yaml
item:
  material: PAPER
  provider: ITEMSADDER
  id: namespace:item_id
```

Providers: `ITEMSADDER`, `ORAXEN`, `NEXO`, `MMOITEMS`. MMOItems uses `TYPE:ID`. The provider must be installed for provider matching.

## Priority and processing

Higher priorities run first. Equal priorities preserve file load order. `stop-processing: true` stops later matching rules after this rule matches; it is different from `actions.cancel`.

## Formatting

Messages accept legacy `&` colors, HEX and MiniMessage formatting supported by the plugin formatter. Player input is not allowed to create privileged click or command events.


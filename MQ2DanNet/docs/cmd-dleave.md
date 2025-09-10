---
tags:
  - command
---

# /dleave

## Syntax

<!--cmd-syntax-start-->
```eqcommand
/dleave <group> [all|save]
```
<!--cmd-syntax-end-->

## Description

<!--cmd-desc-start-->
Leave a group, and optionally write to `[General]` or `[server_character]` (all or save, respectively)
<!--cmd-desc-end-->

## Options

| Option | Description |
|--------|-------------|
| `all` | Remove the group from the `[General]` section of the config file, affecting all characters. |
| `save` | Remove the group from the `[server_character]` section of the config file, affecting a single character. |

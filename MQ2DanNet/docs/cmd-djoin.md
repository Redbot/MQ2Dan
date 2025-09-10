---
tags:
  - command
---

# /djoin

## Syntax

<!--cmd-syntax-start-->
```eqcommand
/djoin <group> [all|save]
```
<!--cmd-syntax-end-->

## Description

<!--cmd-desc-start-->
Join a group, and optionally write to `[General]` or `[server_character]` (all or save, respectively)
<!--cmd-desc-end-->

## Options

| Option | Description |
|--------|-------------|
| `all` | Add the group to the `[General]` section of the config file, having all characters join on next plugin load. |
| `save` | Add the group to the `[server_character]` section of the config file, having just the specific character join the next plugin load. |

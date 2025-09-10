---
tags:
  - command
---

# /dnet

## Syntax

<!--cmd-syntax-start-->
```eqcommand
/dnet [<arg>]
```
<!--cmd-syntax-end-->

## Description

<!--cmd-desc-start-->
Set variables such as network interface, change settings in the config file, toggle debug mode, and output group/peer information. No option will
<!--cmd-desc-end-->

## Options

| Option | Description |
|--------|-------------|
| `(no option)` | Will display available options |
| `interface <iface_name>|clear` | No args will list available interfaces, otherwise will change the network interface to the given interface name, or `clear` to remove the override. |
| `debug [on|off]` | Turn debug on or off. |
| `localecho  [on|off]` | Turn localecho on or off |
| `commandecho  [on|off]` | Turn commandecho on or off |
| `fullnames  [on|off]` | Turn fullnames on or off |
| `frontdelim  [on|off]` | Turn front delimiters on or off |
| `timeout <timeout>` | Sets the /dquery timeout |
| `observedelay <delay>` | Set the delay between observe sends in ms |
| `evasive <timeout>` | Set the evasive timeout in ms |
| `evasiverefresh [on|off]` | Turn evasive refresh on or off |
| `expired <#>` | Set the expired timeout in ms |
| `keepalive <#>` | Set the keepalive time for non-responding peers in ms |
| `info` | Output group/peer information |
| `version` | Will display DanNet version |

---
tags:
  - command
---

# /dquery

## Syntax

<!--cmd-syntax-start-->
```eqcommand
/dquery <name> [-q <query>] [-o <result>] [-t <timeout>]
```
<!--cmd-syntax-end-->

## Description

<!--cmd-desc-start-->
Execute query on name and store return in result.
<!--cmd-desc-end-->

## Options

| Option | Description |
|--------|-------------|
| `-t <timeout>` | How long to wait before timeout. Optional, and the default can be configured. |
| `-q <query>` | A query is simply a normal TLO access from the perspective of the peer with the external `${}`. For example, `Target.ID`. |
| `-o <result>` | Optional; will write the result to `${DanNet.Q}` or `${DanNet.Query}` if omitted. Otherwise it writes to the variable specified (variables are created with `/declare`). If not run from a macro, the result is ignored and just writes out to the TLO. |
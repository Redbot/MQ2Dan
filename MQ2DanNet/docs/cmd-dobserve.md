---
tags:
  - command
---

# /dobserve

## Syntax

<!--cmd-syntax-start-->
```eqcommand
/dobserve <name> [-q <query>] [-o <result>] [-drop]
```
<!--cmd-syntax-end-->

## Description

<!--cmd-desc-start-->
Add an observer on name and update values in result, or drop the observer.
<!--cmd-desc-end-->

## Options

| Option | Description |
|--------|-------------|
| `-q <query>` | A query is simply a normal TLO access from the perspective of the peer with the external `${}`. For example, `Target.ID` |
| `-o <result>` | Optional if no out variable is needed (or not executing from a macro). Variables are created with `/declare`. |
| `-drop` | Drops the observer |

## Examples

**Reading an observer's data**

```
${DanNet[<name>].Observe[<query>]}
```

or

```
${DanNet[<name>].O[<query>]}
```

**Dropping an observer**

```eqcommand
/dobserve <name> -q <query> -drop
```

---
tags:
  - plugin
---
# MQ2DanNet
<!--desc-start-->
This plugin is designed to be a serverless peer network. It is (hopefully) mostly plug and play, and should automatically discover peers for most local network configurations.
<!--desc-end-->

!!! note "Some notes about setup"
    - Some complicated network topologies won't be supported (a server interface is a better solution)  
    - If for some reason the peers aren't self-discovering on a local network  
        - check the output of `/dnet interface`  
        - set one of the discovered interface names with `/dnet interface <name>`  
        - failing that, I'll have to look into why, so contact me with as much info as possible  

### Use

There are 2 basic uses

=== "1. Observer Pattern"

    !!! info "Set up an observer"

    **Methods of setting up an observer:**
    ```
    /dobserve <name> -q <query> [-o <result>]
    ```

    **Reading an observer's data:**
    ```
    ${DanNet[<name>].Observe[<query>]}
    ${DanNet[<name>].O[<query>]}  
    ```

    **Dropping an observer:**
    ```
    /dobserve <name> -q <query> -drop
    ```

    !!! tip "`result` is optional if no out variable is needed (or not executing from a macro)."

=== "2. Direct Query"

    !!! info "Single-use direct query"

    **Submitting a query:**
    ```
    /dquery <name> -q <query> [-o <result>] [-t <timeout>]
    ```

    **Features:**

    - Combines `/delay` with `/varset`
    - `timeout` is optional, and the default can be configured
    - `result` is optional, will just write out the result to `${DanNet.Q}` or `${DanNet.Query}` if omitted
    !!! note "If not run in a macro, ignores `result` and just writes out to the TLO"


### Queries
A query is simply a normal TLO access from the perspective of the peer with the external `${}` stripped
!!! example "Examples"
    - `Me.CurrentMana`
    - `Target.ID`
    - `Me.Current$\{thing}` -- this will evaluate `${thing}` on the peer before sending a response

### Names
A fully-qualified name is `<server>_<character>`, but if you only intend to communicate on your own server, you can ommit the first part and use just `<charactername>` in all these commands.

!!! example "Examples"
    - Locally talk to fatty: `/dtell fatty You smell.`
    - Talk to fatty on the test server: `/dtell test_fatty I can still smell you from this server!`

## Commands

<a href="cmd-djoin/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-djoin.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-djoin.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-djoin.md') }}

<a href="cmd-dleave/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dleave.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dleave.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dleave.md') }}

<a href="cmd-dtell/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dtell.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dtell.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dtell.md') }}

<a href="cmd-dgtell/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dgtell.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dgtell.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dgtell.md') }}

<a href="cmd-dexecute/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dexecute.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dexecute.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dexecute.md') }}

<a href="cmd-dgexecute/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dgexecute.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dgexecute.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dgexecute.md') }}

<a href="cmd-dggexecute/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dggexecute.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dggexecute.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dggexecute.md') }}

<a href="cmd-dgrexecute/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dgrexecute.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dgrexecute.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dgrexecute.md') }}

<a href="cmd-dgzexecute/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dgzexecute.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dgzexecute.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dgzexecute.md') }}

<a href="cmd-dgaexecute/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dgaexecute.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dgaexecute.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dgaexecute.md') }}

<a href="cmd-dggaexecute/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dggaexecute.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dggaexecute.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dggaexecute.md') }}

<a href="cmd-dgraexecute/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dgraexecute.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dgraexecute.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dgraexecute.md') }}

<a href="cmd-dgzaexecute/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dgzaexecute.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dgzaexecute.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dgzaexecute.md') }}

<a href="cmd-dnet/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dnet.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dnet.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dnet.md') }}

<a href="cmd-dobserve/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dobserve.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dobserve.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dobserve.md') }}

<a href="cmd-dquery/">
{% 
  include-markdown "plugins/community-plugins/mq2dannet/cmd-dquery.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "plugins/community-plugins/mq2dannet/cmd-dquery.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('plugins/community-plugins/mq2dannet/cmd-dquery.md') }}

## EQBC to DanNet Cheat Sheets

If you're used to [MQ2EQBC](../mq2eqbc/README.md) and are looking for similar usage with DanNet, here are some concepts/commands that are similar:

=== "Channels vs Groups"

    - `/bccmd channels group1 raid1` -- requires the full list of channels any time you want to join a new channel.  
        - `/djoin` group1 `save` -- join **group1**, store settings in MQ2DanNet.ini under `[server_character]`.  Character will automatically join this group for future sessions.
        - `/djoin` tanks `save` -- join **tanks**, store settings in MQ2DanNet.ini under `[server_character]`.  Character will automatically join this group for future sessions.
        - `/dleave` raid1 `save` -- leave **raid1**, store settings so the character will *not* auto-join next time.

    Rather than adding peers to a group manually, you can use existing commands to add a temporary in-game group/raid setup to a new DanNet group

    - `/dgga /djoin mytempgroup` -- add everyone in your current **group** to *mytempgroup* (add `save` to join in future sessions as well)  
    - `/dgra /djoin mytempraid` -- add everyone in your current **raid**  to *mytempraid*  (add `save` to join in future sessions as well)

=== "Echos"

    **How to echo something in EQBC and DanNet**

    | EQBC                             | DanNet                     |
    |----------------------------------|----------------------------|
    | `/bct <name> //echo something cool`   | `/dt <name> something cool`     |
    | `/bct <channel> //echo something cool`| `/dgt <group> something cool`   |

=== "EQBC to DanNet Commands"

    **Sending commands to your characters**

    | EQBC                             | DanNet                       |
    |----------------------------------|------------------------------|
    | `/bct <name> //command`          | `/dex <name> /command`       |
    | `/bct <channel> //command`       | `/dge <group> /command`      |
    | `/bcg //command`                 | `/dgge /command`             |
    | `/bcga //command`                | `/dgga /command`             |
    | `/bcz //command` (requires netbots)                 | `/dgze /command` (does NOT require netbots)            |
    | `/bcza //command` (requires netbots)                | `/dgza /command` (does NOT require netbots)             |

    With DanNet all of the above are built-in, whereas EQBC requires extra plugins.

## TLO Members
DanNet adds [DanNet](tlo-dannet.md) with the following members. See [Queries](#queries) for use.

{% include-markdown "plugins/community-plugins/mq2dannet/datatype-dannet.md" start="<!--dt-members-start-->" end="<!--dt-members-end-->" %}
{% include-markdown "plugins/community-plugins/mq2dannet/datatype-dannet.md" start="<!--dt-linkrefs-start-->" end="<!--dt-linkrefs-end-->" %}

## INI Entries (MQ2DanNet.ini)

```ini
[General]
Groups=|bgroup|laptop # (1)
Debugging=off # (2)
Local Echo=on # (3)
Command Echo=on # (4)
Full Names=on # (5)
Front Delimiter=off # (6)
Query Timeout=1s # (7)
Observe Delay=1000 # (8)
Evasive=5000 # (9)
Evasive Refresh=off # (10)
Expired=30000 # (11)
Keepalive=30000 # (12)
Tank=war|pal|shd| # (13)
Priest=clr|dru|shm| # (14)
Melee=brd|rng|mnk|rog|bst|ber| # (15)
Caster=nec|wiz|mag|enc| # (16)
[server_character]
Groups=|healrot|rizlona # (17)
```

1. A "|" delimited list of groups for all characters to auto-join, default empty
2. On/off/true/false boolean for debugging output, default off
3. On/off/true/false boolean for local echo, default on
4. On/off/true/false boolean for remote and local command (/dgex, &c) output, default on
5. On/off/true/false boolean for displaying fully-qualified names (on means that all names are displayed as server_character), default on
6. On/off/true/false boolean for putting the | at the front for the TLO output of DanNet.Peers &c, default off
7. Timeout string for implicit delay in /dquery and /dobserve, default is 1s
8. Delay in milliseconds for observation evaluations to be sent, default is 1000
9. Timeout in milliseconds before a peer is considered evasive, default is 5000
10. On/off/true/false, default off
11. Timeout in milliseconds before an unresponsive peer is dropped, default is 30000
12. Timeout in milliseconds to ping the main thread to keep it fresh, default is 30000
13. Short-name class list to auto-join the tank channel, default is war|pal|shd|
14. Short-name class list to auto-join the priest channel, default is clr|dru|shm|
15. Short-name class list to auto-join the melee channel, default is brd|rng|mnk|rog|bst|ber|
16. Short-name class list to auto-join the caster channel, default is nec|wiz|mag|enc|
17. A "|" delimited list of groups for this specific character to auto-join, default empty

### Known Issues
* Proper workgroup permissions are needed for different network groups across PC's (specifically windows 10 with windows 7 machines)
* ZeroMQ has structural issues if something externally closes the TCP sockets that it is using for inter-process communication. If you are getting unexpected crashes after some time running, check your antivirus/firewall software to ensure that it's letting eqgame exist peacefully. Kaspersky is known to close these sockets.
* If you are experiencing crashes loading MQ2Dannet or when zoning, check that your Windows 10 is v1903 or greater (Build 10.0.18362). The MQNext version of MQ2Dannet uses Unix sockets for IPC. Support for this was added to Windows 10 in 2018, but *after* the v1803 public release. As a result the stack crashes when setting up network communications. 
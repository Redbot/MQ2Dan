---
tags:
  - datatype
---
# `DanNet`

<!--dt-desc-start-->
Holds members that return information on peers as well as settings
<!--dt-desc-end-->

## Members
<!--dt-members-start-->
### {{ renderMember(type='string', name='Name') }}

:   current node name (fully qualified)

### {{ renderMember(type='string', name='Version') }}

:   current build version

### {{ renderMember(type='bool', name='Debug') }}

:   debugging flag

### {{ renderMember(type='bool', name='LocalEcho') }}

:   local echo flag (outgoing echo)

### {{ renderMember(type='bool', name='CommandEcho') }}

:   command echo (incoming commands)

### {{ renderMember(type='bool', name='FullNames') }}

:   print fully qualified names

### {{ renderMember(type='bool', name='FrontDelim') }}

:   use a front `|` delimiter in arrays

### {{ renderMember(type='bool', name='ShowGroups') }}

:   show groups?

### {{ renderMember(type='string', name='Timeout') }}

:   timeout for implicit delay in `/dquery` and `/dobserve` commands

### {{ renderMember(type='int', name='ObserveDelay') }}

:   delay between observe broadcasts (in ms)

### {{ renderMember(type='int', name='Evasive') }}

:   time to classify a peer as evasive (in ms)

### {{ renderMember(type='bool', name='EvasiveRefresh') }}

:   if evasiverefresh is on

### {{ renderMember(type='int', name='Expired') }}

:   keepalive time for non-responding peers (in ms)

### {{ renderMember(type='int', name='Keepalive') }}

:   keepalive time for local actor pipe (in ms)

### {{ renderMember(type='int', name='PeerCount') }}

:   number of connected peers

### {{ renderMember(type='string', name='Peers') }}

:   List of connected peers

### {{ renderMember(type='string', name='Peers', params='GroupName') }}

:   List of connected peers in the ${GroupName} group.

### {{ renderMember(type='int', name='GroupCount') }}

:   number of all groups

### {{ renderMember(type='string', name='Groups') }}

:   list of all groups (this includes hidden groups used internally! use Joined if you want only groups that are visible)

### {{ renderMember(type='int', name='JoinedCount') }}

:   number of joined groups

### {{ renderMember(type='string', name='Joined') }}

:   list of joined groups

### {{ renderMember(type='DanObservation', name='Observe', params='query') }}

:   observe accessor, accessed like: `${DanNet[peer_name].Observe[query]}`

    - short version: O  
    - if no indices are specified, lists all queries observers have registered  
    - if only the query is specified, list all peers that have registered that query as an observer on self  
    - if only the peer is specified, list all queries that self has registered on peer  
    - if fully specified, attempt to retrieve the data specified on the remote peer  

### {{ renderMember(type='int', name='ObserveCount') }}

:   short version: OCount  

    - count observed data on peer, or count observers on self if no peer is specified

### {{ renderMember(type='bool', name='ObserveSet') }}

:   short version: OSet  

    - determine if query has been set as observed data on peer, or as an observer on self if no peer specified

### {{ renderMember(type='int64', name='ObserveReceived', params='query') }}

:   Returns timestamp of last received observation.   

    - short version: OReceived

### {{ renderMember(type='DanObservation', name='Query') }}

:   query accessor, for last executed query  

    - short version: Q

### {{ renderMember(type='DanObservation', name='Query', params='query') }}

:   If both peer and query indexes are provided, will return the specific query result. e.g. `${DanNet[mytank].Q[Me.PctHPs]}` If either index is missing, it will return the result of the last query.  

    - short version: Q

### {{ renderMember(type='int64', name='QueryReceived', params='query') }}

:   Returns the timestamp of last received query. 

    - short version: QReceived

<!--dt-members-end-->
## Note
!!! note "Both `Observe` and `Query` are their own data types, which provide a `Received` member to determine the last received timestamp, or 0 for never received. Used like `${DanNet.Q.Received}`"

<!--dt-linkrefs-start-->
[bool]: ../macroquest/reference/data-types/datatype-bool.md
[danobservation]: datatype-danobservation.md
[int]: ../macroquest/reference/data-types/datatype-int.md
[int64]: ../macroquest/reference/data-types/datatype-int64.md
[string]: ../macroquest/reference/data-types/datatype-string.md
<!--dt-linkrefs-end-->

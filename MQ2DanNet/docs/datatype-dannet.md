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
/// member | string Name
current node name (fully qualified)
///

/// member | string Version
current build version
///

/// member | bool Debug
debugging flag
///

/// member | bool LocalEcho
local echo flag (outgoing echo)
///

/// member | bool CommandEcho
command echo (incoming commands)
///

/// member | bool FullNames
print fully qualified names
///

/// member | bool FrontDelim
use a front `|` delimiter in arrays
///

/// member | bool ShowGroups
show groups?
///

/// member | string Timeout
timeout for implicit delay in `/dquery` and `/dobserve` commands
///

/// member | int ObserveDelay
delay between observe broadcasts (in ms)
///

/// member | int Evasive
time to classify a peer as evasive (in ms)
///

/// member | bool EvasiveRefresh
if evasiverefresh is on
///

/// member | int Expired
keepalive time for non-responding peers (in ms)
///

/// member | int Keepalive
keepalive time for local actor pipe (in ms)
///

/// member | int PeerCount
number of connected peers
///

/// member | string Peers
List of connected peers
///

/// member | string Peers[GroupName]
List of connected peers in the ${GroupName} group.
///

/// member | int GroupCount
number of all groups
///

/// member | string Groups
list of all groups (this includes hidden groups used internally! use Joined if you want only groups that are visible)
///

/// member | int JoinedCount
number of joined groups
///

/// member | string Joined
list of joined groups
///

/// member | DanObservation Observe[query]
observe accessor, accessed like: `${DanNet[peer_name].Observe[query]}`

- short version: O  
- if no indices are specified, lists all queries observers have registered  
- if only the query is specified, list all peers that have registered that query as an observer on self  
- if only the peer is specified, list all queries that self has registered on peer  
- if fully specified, attempt to retrieve the data specified on the remote peer  
///

/// member | int ObserveCount
short version: OCount  

- count observed data on peer, or count observers on self if no peer is specified
///

/// member | bool ObserveSet
short version: OSet  

- determine if query has been set as observed data on peer, or as an observer on self if no peer specified
///

/// member | int64 ObserveReceived[query]
Returns timestamp of last received observation.   

- short version: OReceived
///

/// member | DanObservation Query
query accessor, for last executed query  

- short version: Q
///

/// member | DanObservation Query[query]
If both peer and query indexes are provided, will return the specific query result. e.g. `${DanNet[mytank].Q[Me.PctHPs]}` If either index is missing, it will return the result of the last query.  

- short version: Q
///

/// member | int64 QueryReceived[query]
Returns the timestamp of last received query. 

- short version: QReceived
///

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

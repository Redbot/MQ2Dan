---
tags:
  - datatype
---
# `DanObservation`

<!--dt-desc-start-->
Holds information on when a query was last received
<!--dt-desc-end-->

## Members
<!--dt-members-start-->
### {{ renderMember(type='int64', name='Received') }}

:   Timestamp of last received query or observation, e.g. `${DanNet.Query.Received}`<br />You can get a more specific result by providing the query and peer, e.g. `${DanNet[tankname].Query[Me.PctHPs].Received}` or `${DanNet[clericname].Observe[Target.ID].Received}`

<!--dt-members-end-->

<!--dt-linkrefs-start-->
[int64]: ../macroquest/reference/data-types/datatype-int64.md
<!--dt-linkrefs-end-->

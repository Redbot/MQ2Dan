---
tags:
  - tlo
---
# `DanNet`

<!--tlo-desc-start-->
Holds datatypes for DanNet that can query fellow peers and provide information on settings
<!--tlo-desc-end-->

## Forms
<!--tlo-forms-start-->
### {{ renderMember(type='DanNet', name='DanNet') }}
 
### {{ renderMember(type='DanNet', name='DanNet', params='peer') }}

:   Will provide information on the specified peer when used with certain members, such as "Observe". e.g. `${DanNet[peer_name].Observe[query]}`

<!--tlo-forms-end-->

## Associated DataTypes
<!--tlo-datatypes-start-->
## [`DanNet`](datatype-dannet.md)
{% include-markdown "projects/mq2dannet/datatype-dannet.md" start="<!--dt-desc-start-->" end="<!--dt-desc-end-->" trailing-newlines=false %} {{ readMore('projects/mq2dannet/datatype-dannet.md') }}
:    <h3>Members</h3>
    {% include-markdown "projects/mq2dannet/datatype-dannet.md" start="<!--dt-members-start-->" end="<!--dt-members-end-->" %}
    {% include-markdown "projects/mq2dannet/datatype-dannet.md" start="<!--dt-linkrefs-start-->" end="<!--dt-linkrefs-end-->" %}
## [`DanObservation`](datatype-danobservation.md)
{% include-markdown "projects/mq2dannet/datatype-danobservation.md" start="<!--dt-desc-start-->" end="<!--dt-desc-end-->" trailing-newlines=false %} {{ readMore('projects/mq2dannet/datatype-danobservation.md') }}
:    <h3>Members</h3>
    {% include-markdown "projects/mq2dannet/datatype-danobservation.md" start="<!--dt-members-start-->" end="<!--dt-members-end-->" %}
    {% include-markdown "projects/mq2dannet/datatype-danobservation.md" start="<!--dt-linkrefs-start-->" end="<!--dt-linkrefs-end-->" %}
    <!--tlo-datatypes-end-->

    <!--tlo-linkrefs-start-->
    [dannet]: datatype-dannet.md
    <!--tlo-linkrefs-end-->
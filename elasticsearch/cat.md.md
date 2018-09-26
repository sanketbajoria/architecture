GET /_cat/health?v
epoch      timestamp cluster                          status node.total node.data shards pri relo init unassign pending_tasks max_task_wait_time active_shards_percent
1537987931 18:52:11  d3ca5082fe9a477b8497517561e2780f green           3         2     24  12    0    0        0             0                  -                100.0%

GET /_cat/nodes?v
ip             heap.percent ram.percent cpu load_1m load_5m load_15m node.role master name
172.25.133.112           10          97   8    3.92    3.96     3.56 mdi       *      instance-0000000000
172.25.78.179             9          97  16    5.05    5.71     6.40 mdi       -      instance-0000000001
172.25.19.160            24          98  10    1.50    0.82     0.55 m         -      tiebreaker-0000000002

GET /_cat/indices?v
health status index           uuid                   pri rep docs.count docs.deleted store.size pri.store.size
green  open   .kibana         mJqGrIHkQLS3zIrF7aaf4A   1   1          1            0        8kb            4kb
green  open   change_analyzer bKQ80WnRTB2MO6Cu9Ewa5Q   5   1          0            0      2.5kb          1.2kb
green  open   .security-6     -pgH6OIgStC6E0DyzqpknA   1   1                                                  
green  open   product         adssNJKXQBKvf_JUDM7B_g   5   1          0            0      2.5kb          1.2kb

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MTcxMjc0NjZdfQ==
-->
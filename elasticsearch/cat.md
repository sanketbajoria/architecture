## GET /_cat/health?v

epoch      timestamp cluster                          status node.total node.data shards pri relo init unassign pending_tasks max_task_wait_time active_shards_percent
1537987931 18:52:11  d3ca5082fe9a477b8497517561e2780f green           3         2     24  12    0    0        0             0                  -                100.0%

## GET /_cat/nodes?v

ip             heap.percent ram.percent cpu load_1m load_5m load_15m node.role master name
172.25.133.112           10          97   8    3.92    3.96     3.56 mdi       *      instance-0000000000
172.25.78.179             9          97  16    5.05    5.71     6.40 mdi       -      instance-0000000001
172.25.19.160            24          98  10    1.50    0.82     0.55 m         -      tiebreaker-0000000002

## GET /_cat/indices?v

health status index           uuid                   pri rep docs.count docs.deleted store.size pri.store.size
green  open   .kibana         mJqGrIHkQLS3zIrF7aaf4A   1   1          1            0        8kb            4kb
green  open   change_analyzer bKQ80WnRTB2MO6Cu9Ewa5Q   5   1          0            0      2.5kb          1.2kb
green  open   .security-6     -pgH6OIgStC6E0DyzqpknA   1   1                                                  
green  open   product         adssNJKXQBKvf_JUDM7B_g   5   1          0            0      2.5kb          1.2kb

## GET /_cat/allocation?v

shards disk.indices disk.used disk.avail disk.total disk.percent host           ip             node
    12       16.6kb     3.4mb    127.9gb      128gb            0 172.25.133.112 172.25.133.112 instance-0000000000
    12       16.6kb     2.2mb    127.9gb      128gb            0 172.25.78.179  172.25.78.179  instance-0000000001

## GET /_cat/shards?v
index           shard prirep state   docs store ip             node
product         3     r      STARTED    0  261b 172.25.133.112 instance-0000000000
product         3     p      STARTED    0  261b 172.25.78.179  instance-0000000001
product         2     p      STARTED    0  261b 172.25.133.112 instance-0000000000
product         2     r      STARTED    0  261b 172.25.78.179  instance-0000000001
product         1     r      STARTED    0  261b 172.25.133.112 instance-0000000000
product         1     p      STARTED    0  261b 172.25.78.179  instance-0000000001
product         4     p      STARTED    0  261b 172.25.133.112 instance-0000000000
product         4     r      STARTED    0  261b 172.25.78.179  instance-0000000001
product         0     p      STARTED    0  261b 172.25.133.112 instance-0000000000
product         0     r      STARTED    0  261b 172.25.78.179  instance-0000000001
change_analyzer 3     r      STARTED    0  261b 172.25.133.112 instance-0000000000
change_analyzer 3     p      STARTED    0  261b 172.25.78.179  instance-0000000001
change_analyzer 2     p      STARTED    0  261b 172.25.133.112 instance-0000000000
change_analyzer 2     r      STARTED    0  261b 172.25.78.179  instance-0000000001
change_analyzer 1     r      STARTED    0  261b 172.25.133.112 instance-0000000000
change_analyzer 1     p      STARTED    0  261b 172.25.78.179  instance-0000000001
change_analyzer 4     p      STARTED    0  261b 172.25.133.112 instance-0000000000
change_analyzer 4     r      STARTED    0  261b 172.25.78.179  instance-0000000001
change_analyzer 0     p      STARTED    0  261b 172.25.133.112 instance-0000000000
change_analyzer 0     r      STARTED    0  261b 172.25.78.179  instance-0000000001
.security-6     0     p      STARTED            172.25.133.112 instance-0000000000
.security-6     0     r      STARTED            172.25.78.179  instance-0000000001
.kibana         0     p      STARTED    1   4kb 172.25.133.112 instance-0000000000
.kibana         0     r      STARTED    1   4kb 172.25.78.179  instance-0000000001


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkwNTQ3NTI2OF19
-->
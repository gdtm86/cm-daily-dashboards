## Daily Services Dashboard TSQueries

* HDFS-Capacity
```
select dfs_capacity, dfs_capacity_used, dfs_capacity_used_non_hdfs where entityName="HDFS-1"
```
* HDFS-Block Capacity and Total Number of blocks
```
select block_capacity,blocks_total where entityName="HDFS-1"
```
* HDFS-Under Replicated Blocks and Corrupt Replicas
```
select under_replicated_blocks,blocks_with_corrupt_replicas where entityName="HDFS-1"
```
* HDFS-IO
```
select stats(bytes_read_rate_across_datanodes, total), stats(bytes_written_rate_across_datanodes, total) where category = SERVICE and serviceType = HDFS
```
* YARN-Applications Running,Pending,Killed,Failed (Cumulative)
```
select apps_running_cumulative,apps_failed_cumulative_rate,apps_killed_cumulative_rate, apps_pending_cumulative where category=YARN_POOL and serviceName="YARN-1" and queueName=root
```
* YARN-Pending Containers (cumulative)
```
select pending_containers_cumulative where category=YARN_POOL and serviceName="YARN-1" and queueName=root
```
* YARN-Total Containers Running,Failed,Killed Across NodeManagers
```
select total_containers_running_across_nodemanagers, total_containers_failed_rate_across_nodemanagers, total_containers_killed_rate_across_nodemanagers where entityName="YARN-1"
```
* Impala-Total Resident Memory Across Impala Daemons
```
select total_mem_rss_across_impalads where entityName="IMPALA-1"
```
* Impala-Active Frontend API connections
```
select total_thrift_server_beeswax_frontend_connections_in_use_across_impalads, total_thrift_server_hiveserver2_frontend_connections_in_use_across_impalads where entityName="IMPALA-1"
```
* Impala-Frontend API connection rate
```
select total_thrift_server_beeswax_frontend_connections_rate_across_impalads, total_thrift_server_hiveserver2_frontend_connections_rate_across_impalads where entityName="IMPALA-1"
```
* Impala-Total Queries Across Impala Daemons
```
select total_num_queries_rate_across_impalads where entityName="IMPALA-1"
```
* Impala-Completed Impala Queries
```
select stats(num_queries_rate_across_impalads, total) where category = SERVICE and serviceType = IMPALA
```
* Hive-Metastore-JVM Heap Memory Usage
```
select hive_memory_heap_max, hive_memory_heap_used where entityName="HIVE-1-HIVEMETASTORE-ba3c625f560fe2766613840f1d5be5d4"
```
* Hive-Metastore-JVM Pause Time
```
select hive_jvm_pause_time_rate where entityName="HIVE-1-HIVEMETASTORE-ba3c625f560fe2766613840f1d5be5d4"
```
* Hive-Metastore-Open Connections
```
select hive_open_connections where entityName="HIVE-1-HIVEMETASTORE-ba3c625f560fe2766613840f1d5be5d4"
```
* Hive-HiveServer2-JVM heap Memory Usage
```
select hive_memory_heap_max, hive_memory_heap_used where entityName="HIVE-1-HIVESERVER2-ba3c625f560fe2766613840f1d5be5d4"
```
* Hive-HiveServer2-JVM Pause Time
```
select hive_jvm_pause_time_rate where entityName="HIVE-1-HIVESERVER2-ba3c625f560fe2766613840f1d5be5d4"
```
* Hive-HiveServer2-Open Connections
```
select hive_open_connections where entityName="HIVE-1-HIVESERVER2-ba3c625f560fe2766613840f1d5be5d4"
```
* Hive-HiveServer2-Open Operations
```
select hive_open_operations where entityName="HIVE-1-HIVESERVER2-ba3c625f560fe2766613840f1d5be5d4"
```
* Hue-Total users and Active users
```
select hue_users,hue_users_active where roleType = HUE_SERVER and category = ROLE and serviceName = "HUE-1"
```
* Hue-Active Requests
```
select hue_requests_active where roleType = HUE_SERVER and category = ROLE and serviceName = "HUE-1"
```
* Hue-Request Exceptions
```
select integral(hue_requests_exceptions_rate) where roleType = HUE_SERVER and category = ROLE and serviceName = "HUE-1"
```
* Oozie-Jobs Running, Failed and Killed
```
select jobs_running,integral(jobs_failed_rate),integral(jobs_killed_rate) where entityName="OOZIE-1"
```

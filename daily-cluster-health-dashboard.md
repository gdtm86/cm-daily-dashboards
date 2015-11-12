## Daily Cluster Health Dashboard TSQueries

* #### HDFS-Health
```
select health_good_rate * 100 as "good health", health_concerning_rate * 100 as "concerning health", health_bad_rate * 100 as "bad health", health_disabled_rate * 100 as "disabled health", health_unknown_rate * 100 as "unknown health" where entityName="HDFS-1"
```
* #### YARN-Health
```
select health_good_rate * 100 as "good health", health_concerning_rate * 100 as "concerning health", health_bad_rate * 100 as "bad health", health_disabled_rate * 100 as "disabled health", health_unknown_rate * 100 as "unknown health" where entityName="YARN-1"
```
* #### Impala-Health
```
select health_good_rate * 100 as "good health", health_concerning_rate * 100 as "concerning health", health_bad_rate * 100 as "bad health", health_disabled_rate * 100 as "disabled health", health_unknown_rate * 100 as "unknown health" where entityName="IMPALA-1"
```
* #### Hive-Health
```
select health_good_rate * 100 as "good health", health_concerning_rate * 100 as "concerning health", health_bad_rate * 100 as "bad health", health_disabled_rate * 100 as "disabled health", health_unknown_rate * 100 as "unknown health" where entityName="HIVE-1"
```
* #### Hue-HueServer-Health
```
select health_good_rate * 100 as "good health", health_concerning_rate * 100 as "concerning health", health_bad_rate * 100 as "bad health", health_disabled_rate * 100 as "disabled health", health_unknown_rate * 100 as "unknown health" where entityName="HUE-1-HUE_SERVER-ba3c625f560fe2766613840f1d5be5d4"
```
* #### Oozie-Health
```
select health_good_rate * 100 as "good health", health_concerning_rate * 100 as "concerning health", health_bad_rate * 100 as "bad health", health_disabled_rate * 100 as "disabled health", health_unknown_rate * 100 as "unknown health" where entityName="OOZIE-1"
```
* #### Physical-Memory-Used-Across-Hosts
```
select total_physical_memory_total_across_hosts, total_physical_memory_used_across_hosts where category = CLUSTER
```
* #### Cluster Disk IO
```
select stats(read_bytes_rate_across_disks, total), stats(write_bytes_rate_across_disks, total) where category = CLUSTER
```
* #### Cluster CPU
```
select cpu_percent_across_hosts where category = CLUSTER
```
* #### Cluster Network IO
```
select stats(bytes_receive_rate_across_network_interfaces, total), stats(bytes_transmit_rate_across_network_interfaces, total) where category = CLUSTER
```
* #### Total-Disk-IO-Utilization
```
select total_utilization_across_disks where category = CLUSTER
```
* #### Impala-Important-Events-And-Alerts
```
select integral(alerts_rate), integral(events_critical_rate), integral(events_important_rate) where entityName="IMPALA-1"
```
* #### HDFS-Important-Events-And-Alerts
```
select integral(alerts_rate), integral(events_critical_rate), integral(events_important_rate) where serviceType=HDFS AND clusterId="1" and category = SERVICE
```
* #### YARN-Important-Events-And-Alerts
```
select integral(alerts_rate), integral(events_critical_rate), integral(events_important_rate) where entityName="YARN-1"
```
* #### Hive-Important-Events-And-Alerts
```
select integral(alerts_rate), integral(events_critical_rate), integral(events_important_rate) where entityName="HIVE-1"
```
* #### Hue-Important-Events-And-Alerts
```
select integral(alerts_rate), integral(events_critical_rate), integral(events_important_rate) where entityName="HUE-1"
```
* #### Oozie-Important-Events-And-Alerts
```
select integral(alerts_rate), integral(events_critical_rate), integral(events_important_rate) where entityName="OOZIE-1"
```

---
id: jvm  
title: Monitor：JVM      
sidebar_label: JVM
---

> Collect and monitor the general performance Metrics of JVM.

**Protocol Use：JMX**

### Configuration parameter

| Parameter name      | Parameter help description |
| ----------- | ----------- |
| Monitoring Host     | Monitored IPV4, IPV6 or domain name. Note⚠️Without protocol header (eg: https://, http://) |
| Monitoring name     | Identify the name of this monitoring. The name needs to be unique |
| Port        | Port provided by JMX |
| Username      | JMX connection user name, optional |
| Password       | JMX connection password, optional |
| Collection interval   | Interval time of monitor periodic data collection, unit: second, and the minimum interval that can be set is 10 seconds |
| Whether to detect    | Whether to detect and check the availability of monitoring before adding monitoring. Adding and modifying operations will continue only after the detection is successful |
| Description remarks    | For more information about identifying and describing this monitoring, users can note information here |

### Collection Metrics

#### Metrics Set：memory_pool

| Metric name      | Metric unit | Metric help description |
| ----------- | ----------- | ----------- |
| name         |  | metrics name |
| committed            | kb | total size |
| init         | kb | init size |
| max | kb | max size |
| used         | kb | used size |

#### Metrics Set：code_cache

| Metric name      | Metric unit | Metric help description |
| ----------- | ----------- | ----------- |
| committed            | kb | total size |
| init         | kb | init size |
| max | kb | max size |
| used         | kb | used size |

#### Metrics Set：class_loading

| Metric name      | Metric unit | Metric help description |
| ----------- | ----------- | ----------- |
| LoadedClassCount            |  | Loaded Class Count |
| TotalLoadedClassCount        |  | Total Loaded Class Count |
| UnloadedClassCount |  | Unloaded Class Count |


#### Metrics Set：thread

| Metric name      | Metric unit | Metric help description |
| ----------- | ----------- | ----------- |
| TotalStartedThreadCount            |  | Total Started Thread Count |
| ThreadCount        |  | Thread Count |
| PeakThreadCount |  | Peak Thread Count |
| DaemonThreadCount |  | Daemon Thread Count |
| CurrentThreadUserTime | ms | Current Thread User Time |
| CurrentThreadCpuTime | ms | Current Thread Cpu Time |

### JVM App Enable JMX Protocol 

1. Add JVM `VM options` When Start Server

```shell
-Dcom.sun.management.jmxremote.port=9999
-Dcom.sun.management.jmxremote.ssl=false
-Dcom.sun.management.jmxremote.authenticate=false 
```


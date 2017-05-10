* What is ubertask optimization?
  ```
  Whether to enable ubertask optimization, which runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.
  ```
* Where in CM is the Kerberos Security Realm value displayed?
  ```
  Administration -> Settings ->  Category -> Kerberos -> security_realm
  ```
* Which CDH service(s) host a property for enabling Kerberos authentication?
  ```
  Namenode
  ResourceManager
  ```
* How do you upgrade the CM agents?
  ```
  a. upgrade the CM server
  b. Hosts -> Re-run Upgrade Wizard
  ```
* Give the `tsquery` statement used to chart Hue's CPU utilization?
  ```
  SELECT cpu_percent WHERE roleType=HUE_SERVER
  ```
* Name all the roles that make up the Hive service
  ```
  hiveserver2
  hive metastore
  hive gateway
  ```
* What steps must be completed before integrating Cloudera Manager with Kerberos?
  ```
  Install KDC and kerberos libs
  ```

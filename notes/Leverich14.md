Paper Title
Reconciling High Server Utilization and Sub-millisecond Quality-of-Service

Author(s)
Jacob Leverich, Christos Kozyrakis

Date
01.22.15

Novel Idea
With a thorough analysis with memcached(as a latency sensitive workload) the authors identify QoS vulnerabilities when server hosts multiple tasks. And try to remove that bottleneck with changing. Their solutions are 1)Pinning the memcached threads to distinct cores and 2)Change and optimize the scheduler of Linux OS from CFS to BVT. The authors try to show interference aware scheduling can achieve higher server utilization.

Main Result(s)
Can achieve relatively good performance with memcached and 1ms task with specified interference aware task scheduling.

Impact
With interference aware task scheduling, customer can actually achieve higher server utilization despite of QoS restriction. This can also affect to Environmental, regulatory, and economic concerns.

Evidence
They evaluate performance with changing QPS of memcached and 1ms latency-sensitive task. And memcached's QoS is mostly satisfied.

Prior work
QoS for colocated workloads in warehouse-scale datacenters. - The authors more focused on the overall impact on load provisioning. 

Competitive work
Nope

Reproducibility
I think it's easily reproducable since they use well-known memcached as target application.

Question
Is this interference aware scheduling is applicable also to other workloads?


Criticism
Too specific environment.

Ideas for further work

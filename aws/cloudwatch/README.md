\# Amazon CloudWatch Monitoring



\## Purpose



CloudWatch is used to monitor the performance of the EC2 web servers after deployment.



\## Metric



Primary metric:



`CPUUtilization`



Statistic:



`Average`



Period:



`5 minutes`



\## CPU Alarms



Three high-CPU alarms were configured:



\- `WebFarm-Web01-HighCPU`

\- `WebFarm-Web02-HighCPU`

\- `WebFarm-Web03-HighCPU`



Threshold:



\*\*CPU utilization > 70%\*\*



\## Objective



The monitoring configuration provides visibility into web-server performance and can help identify workloads that require right-sizing or additional capacity.




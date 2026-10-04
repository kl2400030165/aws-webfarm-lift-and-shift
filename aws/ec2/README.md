\# Amazon EC2 Web Farm



\## Purpose



Amazon EC2 hosts the web-server instances used for the working AWS web-farm demonstration.



\## Active Demonstration Servers



\### Web Server 01

\- Name: `MIGRATED-WEB-01`

\- Instance Type: `t3.micro`

\- Application: TechStore

\- Web Server: Apache



\### Web Server 02

\- Name: `MIGRATED-WEB-02`

\- Instance Type: `t3.micro`

\- Application: TechStore

\- Web Server: Apache



\### Web Server 03

\- Name: `MIGRATED-WEB-03`

\- Instance Type: `t3.micro`

\- Application: TechStore

\- Web Server: Apache



\## Web Farm



All three instances are registered with the `webfarm-targets` Application Load Balancer target group.



Current health:



\*\*3/3 Healthy\*\*



\## Scaling



The architecture is designed to scale toward the original eight-server target. The current live demonstration uses three servers because of the AWS account's vCPU capacity limitation.


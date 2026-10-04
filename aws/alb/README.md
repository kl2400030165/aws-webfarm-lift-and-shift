\# Application Load Balancer



\## Purpose



The Application Load Balancer provides a single entry point for users and distributes HTTP traffic across the AWS web farm.



\## Configuration



\- Load Balancer: `webfarm-alb`

\- Type: Application Load Balancer

\- Scheme: Internet-facing

\- IP Type: IPv4

\- Listener: HTTP :80

\- Availability Zones: 2

\- Security Group: `ALB-SG`



\## Target Group



\- Name: `webfarm-targets`

\- Protocol: HTTP

\- Port: 80

\- Health Check Path: `/`



\## Healthy Targets



\- `MIGRATED-WEB-01`

\- `MIGRATED-WEB-02`

\- `MIGRATED-WEB-03`



Current target health:



\*\*3/3 Healthy\*\*



\## Validation



Traffic distribution was verified by accessing the ALB DNS name and refreshing the application.



The TechStore application displays the identity of the server handling the request, allowing Web Server 01, Web Server 02 and Web Server 03 to be observed during the demonstration.




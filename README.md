\# AWS Application Migration Service – Lift-and-Shift Web Farm



\## 📌 Project Overview



This project demonstrates a practical lift-and-shift migration workflow for a web workload using \*\*AWS Application Migration Service (MGN)\*\*.



A simulated on-premises web server is replicated to AWS using the MGN replication agent. The AWS environment then demonstrates a scalable web-farm architecture using Amazon EC2, Application Load Balancer, Target Groups, VPC networking, Security Groups, and Amazon CloudWatch.



\---



\## 🎯 Objectives



\- Demonstrate server rehosting using AWS Application Migration Service

\- Replicate a source web server to AWS

\- Build a multi-AZ AWS web-farm architecture

\- Distribute application traffic using an Application Load Balancer

\- Monitor EC2 performance using Amazon CloudWatch

\- Demonstrate a scalable architecture for an eight-server web farm

\- Validate the migrated application in AWS



\---



\## 🏗️ Architecture



```text

&#x20;                        USERS

&#x20;                          |

&#x20;                          v

&#x20;               Application Load Balancer

&#x20;                          |

&#x20;                   Web Farm Target Group

&#x20;                   /         |         \\

&#x20;                  /          |          \\

&#x20;                 v           v           v

&#x20;            EC2 Web-01  EC2 Web-02  EC2 Web-03

&#x20;                 \\          |          /

&#x20;                  \\         |         /

&#x20;                   +--------+---------+

&#x20;                            |

&#x20;                      CloudWatch

&#x20;                    Metrics + Alarms





&#x20;      SIMULATED ON-PREMISES SOURCE

&#x20;                 |

&#x20;            MGN Agent

&#x20;                 |

&#x20;                 v

&#x20;      AWS Application Migration Service

&#x20;                 |

&#x20;         Initial Replication

&#x20;                 |

&#x20;               8/8 GiB

&#x20;                 |

&#x20;         Ready for Testing



| AWS Service | Purpose |

|---|---|

| AWS Application Migration Service | Server replication and migration |

| Amazon EC2 | Web-server compute |

| Amazon VPC | Network isolation |

| Subnets | Network segmentation |

| Internet Gateway | Internet connectivity |

| Route Tables | Network traffic routing |

| Security Groups | Resource-level firewall |

| Application Load Balancer | Traffic distribution |

| Target Group | Backend web-server pool |

| Amazon CloudWatch | Monitoring and alarms |

| Amazon EBS | EC2 block storage |

| IAM | Access control |



🔄 Migration Workflow

1\. Prepare AWS networking and security

2\. Configure the simulated source web server

3\. Install the AWS MGN replication agent

4\. Register the source server

5\. Perform initial block-level replication

6\. Verify replication status

7\. Reach Ready for Testing

8\. Validate the AWS web-farm environment

9\. Monitor the application using CloudWatch

🚀 Implementation Results

AWS MGN

\- Source server: SOURCE-WEB-01

\- Replication type: Agent-based

\- Initial replication: Completed

\- Total replicated storage: 8/8 GiB

\- Lifecycle reached: Ready for Testing

AWS Web Farm

\- MIGRATED-WEB-01

\- MIGRATED-WEB-02

\- MIGRATED-WEB-03

Load Balancing

\- Application Load Balancer: webfarm-alb

\- Target Group: webfarm-targets

\- Healthy targets: 3/3

\- Availability Zones: 2

\- HTTP listener: Port 80

Monitoring

CloudWatch CPU monitoring and alarms were configured for all three web servers:

\- WebFarm-Web01-HighCPU

\- WebFarm-Web02-HighCPU

\- WebFarm-Web03-HighCPU

CPU alarm threshold:

70%

🖥️ Application

The project uses a demonstration TechStore web application hosted on Apache.

The application includes:

\- Product catalog

\- Order information

\- Infrastructure status

\- Web-server identity

\- Migration information

\- AWS web-farm status

The business values displayed in the application are demonstration data.

🔀 Load Balancing Demonstration

The application identifies the server handling each request.

Example:

Request → ALB → Web Server 01

Request → ALB → Web Server 02

Request → ALB → Web Server 03



This allows live traffic distribution to be visually demonstrated during the project review.

📊 Monitoring

Amazon CloudWatch is used to monitor EC2 CPU utilization.

High CPU alarms were configured for all three web servers.

This provides operational visibility and can help identify performance issues after migration.

⚠️ Implementation Limitations

The original project requirement targets an eight-server web farm.

The current live demonstration uses three web servers because of the AWS account's EC2 vCPU capacity limitation.

During the MGN test-launch stage, the MGN conversion server attempted to use an m5.large instance, which was rejected by the account's instance eligibility restriction.

Therefore:

\- Initial MGN replication was successfully completed.

\- The source reached Ready for Testing.

\- Automated MGN test launch was not successfully completed.

\- MGN cutover was not completed.

\- The working web-farm demonstration was implemented using three EC2 instances.

The current MGN source status may show Stalled because the source server was subsequently stopped after initial replication.

📈 Target Scalable Architecture

The architecture is designed to scale toward the original eight-server requirement:

&#x20;                        ALB

&#x20;                         |

&#x20;      +------------------+------------------+

&#x20;      |                  |                  |

&#x20;    Web-01             Web-02             Web-03

&#x20;      |                  |                  |

&#x20;    Web-04             Web-05             Web-06

&#x20;      |                  |                  |

&#x20;    Web-07             Web-08



Additional production enhancements could include:

\- Auto Scaling Groups

\- HTTPS with AWS Certificate Manager

\- Route 53 custom domain

\- AWS WAF

\- RDS Multi-AZ

\- Centralized logging

\- Automated migration cutover

\- Advanced CloudWatch dashboards

🧪 Validation

The implementation was validated through:

\- MGN replication verification

\- EC2 health checks

\- Target Group health checks

\- Application Load Balancer connectivity

\- Live traffic distribution

\- TechStore application accessibility

\- CloudWatch CPU monitoring



AWS project/

│

├── architecture/

├── application/

│   └── techstore/

├── aws/

│   ├── network/

│   ├── mgn/

│   ├── ec2/

│   ├── alb/

│   └── cloudwatch/

├── screenshots/

├── docs/

├── .gitignore

└── README.md



Team

Y24-SAA-Team391

Project Code: 24CC3014-P109


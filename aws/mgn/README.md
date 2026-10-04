\# AWS Application Migration Service (MGN)



\## Purpose



AWS Application Migration Service (MGN) was used to replicate the simulated on-premises source server to AWS.



\## Source Server



\- Name: `SOURCE-WEB-01`

\- Operating System: Amazon Linux 2023

\- Web Server: Apache HTTP Server

\- Migration Strategy: Rehost / Lift-and-Shift



\## Replication



The AWS MGN replication agent was installed on the source server.



Initial replication completed successfully:



\- Replication Type: Agent-based

\- Total Replicated Storage: 8/8 GiB

\- Initial Replication: Finished

\- Lifecycle: Ready for Testing



\## Current Status



The source server was later stopped because of the AWS account EC2 vCPU limitation. As a result, the current MGN replication state may show `Stalled`.



The stalled state occurred after the initial 8/8 GiB replication had already completed.



\## Test Launch Limitation



During the MGN test-launch stage, the MGN conversion server attempted to use an `m5.large` instance. The AWS account's instance eligibility restriction rejected the request.



Therefore, automated MGN test launch and cutover were not completed in the current environment.


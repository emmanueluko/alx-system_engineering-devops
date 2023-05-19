**My First Postmortem**

**Issue Summary:**
On May  7th, 2023, from 12:30 AM and 3:00 AM WAT, our web application experienced a technical error, affecting approximately 30% of our users. During this time, users were unable to access certain features of the application, resulting in reduced functionality.

**Timeline:**
•	12:30 AM: Our monitoring system detected a spike in error rates on the web servers.
•	1:05 AM: An engineer received a notification from the monitoring system and began investigating.
•	1:10 AM: The engineer noticed that the database was experiencing high CPU usage and suspected a query was causing the issue.
•	1:15 AM: The engineer began investigating slow query logs and optimizing the queries.
•	2:00 AM: After optimizing the queries, the issue persisted. The engineer escalated the issue to the database team.
•	2:15 AM: The database team identified a deadlock between two queries and resolved the issue.
•	2:30 AM: The application was tested and verified to be functioning properly.
•	3:00 AM: The incident was declared and marked resolved.

**Root Cause and Resolution:**
The root cause of the partial outage was a deadlock between two queries in the database, which caused high CPU usage and slowed down the entire system. The deadlock occurred due to a race condition that was triggered by a recent code change.
To resolve the issue, the database team analyzed the deadlock and identified the queries that were causing it. They then optimized the queries to eliminate the race condition and prevent similar issues from occurring in the future.

**Corrective and Preventative Measures:**
To prevent similar incidents from occurring in the future, we will take the following actions:

•	Implement a more robust testing process for code changes to catch potential race conditions before deployment.

•	Increase monitoring and alerting for database performance metrics to detect issues before they impact users.

•	Improve documentation and communication among teams to facilitate faster incident resolution.

Specific tasks to address the issue include:

•	Review recent code changes and identify potential race conditions.

•	Implement more extensive testing for code changes that involve database queries.

•	Implement additional monitoring and alerting for database performance metrics.

•	Document the incident and share the lessons learned with the team to improve incident response and prevent similar incidents from occurring in the future.

**Misleading Investigation/Debugging Paths:**
During the initial investigation, the engineer suspected that slow queries were causing the issue and spent considerable time optimizing them. However, this turned out to be a misleading path, as the root cause was a deadlock between two queries that were not detected by the slow query logs. In retrospect, more extensive testing and monitoring could have caught the issue earlier and saved time on investigation.

**Escalation:**
The incident was initially handled by an engineer, who escalated it to the database team when they were unable to resolve the issue. The database team was able to quickly identify the root cause and resolve the issue, resulting in a speedy resolution.

**Conclusion:**
We take incidents like this very seriously and are committed to improving our processes to prevent similar incidents from occurring in the future. We apologize for any inconvenience this may have caused our users and will continue to work towards providing a stable and reliable service.


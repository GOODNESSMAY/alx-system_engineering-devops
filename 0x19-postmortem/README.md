Postmortem: Web Stack Outage Incident
Issue Summary
Duration: May 10, 2024, 14:00 - 16:30 (UTC-07:00)

Impact:

The user authentication service experienced a complete outage.
Users were unable to log in, affecting approximately 30% of our active users.
High-profile customers reported the issue, leading to increased urgency.
Root Cause:

A misconfigured firewall rule inadvertently blocked traffic to the authentication service.
Timeline
14:00: Issue detected by monitoring alerts showing a sudden drop in successful login requests.
14:15: Engineers noticed the issue when investigating slow response times for other services.
14:30: Investigation focused on the authentication service logs and network configuration.
14:45: Initial assumption: Database overload due to increased traffic.
15:00: Debugging path: Optimized database queries, but no improvement.
15:15: Escalated to the network team for further analysis.
15:30: Firewall logs revealed the misconfigured rule blocking incoming traffic.
15:45: Corrective action: Disabled the problematic firewall rule.
16:00: Service restored after rule adjustment.
16:30: Incident resolved; users regained access.
Root Cause and Resolution
Root Cause:
Misconfigured Firewall Rule:
A recent network update introduced a restrictive firewall rule.
The rule blocked incoming traffic to the authentication service.
No monitoring alerts were triggered due to the specific nature of the rule.
Resolution:
Firewall Rule Adjustment:
Disabled the problematic rule.
Verified that traffic flowed correctly to the authentication service.
Implemented additional monitoring to prevent similar issues.
Corrective and Preventative Measures
Review Firewall Rules:
Regularly audit and validate firewall rules.
Implement change management processes to prevent accidental misconfigurations.
Enhance Monitoring:
Set up alerts for specific rule violations.
Monitor critical services more closely.
Documentation and Training:
Document network changes comprehensively.
Train engineers on proper firewall rule management.
Automated Testing:
Integrate automated tests for critical services during deployment.
Include firewall rule checks in the test suite.

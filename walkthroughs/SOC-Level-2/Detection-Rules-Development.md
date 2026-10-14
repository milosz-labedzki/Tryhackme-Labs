* `Data source` - Raw logs flowing through the system that do not provide enough context on their own about malicious activity.


* `Detection logic` - The logical chain connecting different events to identify a potential attack pattern.


* `Trigger condition` - The specific threshold or condition that turns suspicious data analysis into an official alert.


* `Metadata` - Descriptive labels like names and descriptions that help analysts quickly understand the alert context.


* `Response action` - The defensive reaction taken after a rule triggers to stop the threat, such as blocking a suspicious IP address.


* `eventID 4625` - A Windows security log indicating a failed user login attempt.


* `eventID 4624` - A Windows security log indicating a successful user login attempt.


* `Atomic Detections` - Detection rules that evaluate a single, isolated event at the exact moment it occurs without requiring historical context.


* `Stateful Detection` - Advanced detection methods that maintain memory and track patterns across multiple events and timelines, such as tracking failures over time.

<h1>Incident Report Analysis - DDoS</h1>
<h2>Description</h2>

An incident report analysis following an apparent distributed denial of service, using the NIST CSF.

<h2>Incident Summary</h2>

The organization experienced a security event when all network services stopped responding suddenly. The security team found the disruption was caused by a DDoS attack through a flood of incoming ICMP packets. The team blocked the attack and began restoring critical network services.

<h2>NIST CSF</h2>

| Function |  |
| --- | --- |
| Identify | A malicious actor targeted the company with an ICMP flood attack, affecting the entire network. All critical resources needed to be secured and restored to a functioning state. |
| Protect | The security team implemented a new firewall rule to limit the rate of incoming ICMP packets. A NIDPS was also implemented to filter out some ICMP traffic based on suspicious characteristics. |
| Detect | The team configured source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets. They also implemented network monitoring software to detect anomalous traffic. |
| Respond | In future security events, the security team will isolate affected systems to prevent further disruption to the network; they will attempt to restore any critical systems and services disrupted by the event. Following this, the team will analyze network logs to check for suspicious and abnormal activity, reporting flagged activity to upper management when applicable. |
| Recover | To recover from an ICMP flood DDoS attack, access to network services need to be restored to a previous functioning state. In the future, ICMP flood attacks should be captured at the configured firewall. Then, all non-critical network services should be stopped to reduce internal network traffic. Critical network services should be restored first. Once the flood of ICMP packets times out, non-critical systems and services can be brought back online. |

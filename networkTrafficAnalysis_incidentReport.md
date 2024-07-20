<h1>Cybersecurity Incident Report: Network Traffic Analysis</h1>

![image](https://github.com/user-attachments/assets/57957bb7-c827-480d-a086-9f40e339055f)

<h2>Summary of problem</h2>

The UDP protocol reveals that the DNS server used by the company website "[www.yummyrecipesforme.com]()” is unreachable.

This is based on the results of the network analysis, which show that the ICMP echo reply returned the error message “udp port 53 unreachable” 

The port noted in the error message is used for DNS protocol traffic, which looks up the IP address associated with domain names.

The most likely issue is that the DNS server used by “[www.yummyrecipesforme.com]()” is not responding to requests.

<h2>Analysis of incident</h2>

The incident occurred early this afternoon

The IT team became aware of the incident when several customers called reporting that they were unable to access the company website “www.yummyrecipesforme.com,” seeing the error “destination port unreachable.”

Network security professionals at our company visited the website themselves and received the same error. At 1:24pm they used the network analyzer tool tcpdump to sniff outgoing packets.

The resulting pcap showed the error “udp port 53 unreachable” and continued to show the same error message a total of three times on three separate attempts. 

The DNS server may be down or traffic to port 53 may be blocked by a misconfigured firewall. If the DNS server is down, the cause may be a DoS attack conducted by a malicious actor.

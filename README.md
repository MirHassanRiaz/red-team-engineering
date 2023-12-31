# Red Team Engineering

# NMAP Scanning Obfuscation
If an HTTP user agent isn't set at the time of running the given Nmap script, the logs on the target system could log a user agent containing Nmap Scripting Engine. This can be mitigated using the option --script-args http.useragent="CUSTOM_AGENT"

![image](https://github.com/MirHassanRiaz/red-teaming-arsenal/assets/53171887/0b2ee5f9-ee05-4eb5-8c69-85ee34d34bd0)

# The OPSEC process has five steps

1. Identify critical information
2. Analyse threats
3. Analyse vulnerabilities
4. Assess risks
5. Apply appropriate countermeasures

![image](https://github.com/MirHassanRiaz/red-team-engineering/assets/53171887/855eb5fc-0351-441b-b9fc-e79033ed22e6)

https://www.esd.whs.mil/Portals/54/Documents/DD/issuances/dodm/520502m.pdf

# Examples of threats

![image](https://github.com/MirHassanRiaz/red-team-engineering/assets/53171887/e6ece97f-cd58-4efc-a592-ee8ee1e65eea)

# Examples of vulnerabilities

![image](https://github.com/MirHassanRiaz/red-team-engineering/assets/53171887/ffd7d8d5-47dc-4d44-9e5a-ad19f4df8152)

You use Nmap to discover live hosts on a target subnet and find open ports on live hosts. Moreover, you send various phishing emails leading the victim to a phishing webpage you're hosting. Furthermore, you're using the Metasploit framework to attempt to exploit certain software vulnerabilities. These are three separate activities; however, if you use the same IP address(es) to carry out these different activities, this would lead to an OPSEC vulnerability. Once any hostile/malicious activity is detected, the blue team is expected to take action, such as blocking the source IP address(es) temporarily or permanently. Consequently, it would take one source IP address to be blocked for all the other activities use this IP address to fail. In other words, this would block access to the destination IP address used for the phising server, and the source IP address using by Nmap and Metasploit Framework.

Another example of an OPSEC vulnerability would be an unsecured database that's used to store data received from phishing victims. If the database is not properly secured, it may lead to a malicious third party compromising the operation and could result in data being exfiltrated and used in an attack against your client's network. As a result, instead of helping your client secure their network, you would end up helping expose login names and passwords.

# Examples of risks

Let’s revisit the two examples from the previous task. In the first example, we considered the vulnerability of scanning the network with Nmap, using the Metasploit framework, and hosting the phishing pages using the same public IP address. We analysed that this is a vulnerability as it makes it easier for the adversary to block our three activities by simply detecting one activity. Now let’s assess this risk. To evaluate the risk related to this vulnerability, we need to learn the possibility of one or more of these activities being detected. We cannot answer this without obtaining some information about the adversary’s capabilities. Let’s consider the case where the client has a Security Information and Event Management (SIEM) in place. A SIEM is a system that allows real-time monitoring and analysis of events related to security from different sources across the network. We can expect that a SIEM would make it reasonably uncomplicated to detect suspicious activity and connect the three events. As a result, we would assess the related risk as high. On the other hand, if we know that the adversary has minimal resources for detecting security events, we can assess the risk related to this vulnerability as low.

Let’s consider the second example of an unsecured database used to store data received from a phishing page. Based on data collected from several research groups using honeypots, we can expect various malicious bots to actively target random IP addresses on the Internet. Therefore, it is only a matter of time before a system with weak security is discovered and exploited.

![image](https://github.com/MirHassanRiaz/red-team-engineering/assets/53171887/0c600932-192a-4c27-88ee-d9d35b390dcc)

https://csrc.nist.gov/glossary/term/risk_assessment

# Examples of counter measures

Let’s revisit the two examples we presented in the Vulnerability Analysis task. In the first example, we considered the vulnerability of running Nmap, using the Metasploit framework, and hosting the phishing pages using the same public IP address. The countermeasure for this one seems obvious; use a different IP address for each activity. This way, you can ensure that if one activity was detected the public IP address is blocked, the other activities can continue unaffected.

In the second example, we considered the vulnerability of an unsecured database used to store data received from a phishing page. From a risk assessment perspective, we considered it as high risk due to malicious third parties potentially looking for random easy targets. The countermeasure, in this case, would be to ensure that the database is adequately secured so that the data cannot be accessed except by authorized personnel.

https://www.esd.whs.mil/Portals/54/Documents/DD/issuances/dodm/520502m.pdf

<a href="https://www.linkedin.com/in/emilio-mardones" target="_blank">
  <img src="https://upload.wikimedia.org/wikipedia/commons/c/ca/LinkedIn_logo_initials.png" alt="LinkedIn Badge" width="24" height="24" />
</a>
<a href="https://ofendor.github.io/portfolio1/" target="_blank">
  <img src="https://upload.wikimedia.org/wikipedia/commons/9/91/Octicons-mark-github.svg" alt="GitHub Badge" width="24" height="24" />
</a>
<a href="https://coursera.org/share/38ab1d68036cb56bc093082ab335d0c1" target="_blank">
  <img src="https://www.clipartmax.com/png/small/219-2198126_contract-education-degree-certificate-diploma-certificate-icon.png" alt="Contract, Education, Degree, Certificate, Diploma, - Certificate Icon @clipartmax.com" width="24" height="24">
</a>
<a href="mailto:random@gmail.com" target="_blank">
  <img src="https://www.clipartmax.com/png/small/31-316827_gmail-icon-gmail-icon.png" alt="Gmail Icon" width="24" height="24">
</a>

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Analysing Network Communications</p>

<pre><code style="color: #ff3f31;">Portfolio Activity 1 - DNS and ICMP Traffic Analysis</code></pre>
In this project, I used the information provided by a network protocol analyser to examine DNS and ICMP traffic, focusing on identifying potential security threats. By analysing IP addresses in the TCP/IP model, I gained valuable insight into suspicious data packets and learned how to detect and mitigate risks in a network traffic. 

<p style="font-size: 12px; font-style: italic; color: #4a4a4a;">
  All portfolio items represent fictional companies, IP addresses, websites, and emails, used strictly for educational purposes; and provided hands-on experience in real-world cybersecurity practices.  
</p>

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Activity Overview</p>
Working as a Cyber Security Analyst in a company that provides IT services, I receive reports from clients saying that they were not able to access the client company's website www.plantbasedrecipes.com, and saw the error "destination port unreachable" after waiting for the page to load.
I was tasked with analysing the situation and determine which network protocol was affected during this incident. To start, I use a network analyser tool, `tcpdump`, and attempt to load the webpage. The analyser showed that when I send UDP packets to the DNS server, I receive ICMP packets containing the error message: "udp port 53 unreachable". With the information provided, I wrote a follow-up report.


<p style="font-size: 12px; font-style: italic; color: #4a4a4a;">
  This project reflects my growing expertise in network security and protocol analysis, and my commitment to building a strong foundation for a future cybersecurity career.
</p>

<pre style="background-color: #2d1b52; font-size: 10px;"><code style="color: #9d9da1;">
<span style="color:#00ff9c;">13:24:32.192571</span> IP <span style="color:#ff2079;">192.51.100.15.52444</span> > <span style="color:#fffb00;">203.0.113.2</span>.domain: 35084+ A? plantbasedrecipes.com. (24)
<span style="color:#00ff9c;">13:24:36.098564</span> IP <span style="color:#ff2079;">203.0.113.2</span> > <span style="color:#fffb00;">192.51.100.15</span>: <span style="color:#fbff00;">ICMP</span> <span style="color:#ff2079;">203.0.113.2</span> udp port 53 unreachable length 254
<span style="color:#00ff9c;">13:26:32.192571</span> IP <span style="color:#ff2079;">192.51.100.15.52444</span> > <span style="color:#ff2079;">203.0.113.2</span>.domain: 35084+ A? plantbasedrecipes.com. (24)
<span style="color:#00ff9c;">13:27:15.934126</span> IP <span style="color:#ff2079;">203.0.113.2</span> > <span style="color:#ff2079;">192.51.100.15</span>: <span style="color:#fbff00;">ICMP</span> <span style="color:#ff2079;">203.0.113.2</span> udp port 53 unreachable length 320
<span style="color:#00ff9c;">13:28:32.192571</span> IP <span style="color:#ff2079;">192.51.100.15.52444</span> > <span style="color:#ff2079;">203.0.113.2</span>.domain: 35084+ A? plantbasedrecipes.com. (24)
<span style="color:#00ff9c;">13:28:50.022967</span> IP <span style="color:#ff2079;">203.0.113.2</span> > <span style="color:#ff2079;">192.51.100.15</span>: <span style="color:#fbff00;">ICMP</span> <span style="color:#ff2079;">203.0.113.2</span> udp port 53 unreachable length 150
</code></pre>

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Report</p>

| **Summary of the problem found in the tcpdump log** | 
|----------------------------------------------------|
| As shown in the data log above, the UDP protocol contacted the DNS server to retrieve the IP address that hosts the domain name of `plantbasedrecipes.com`. The ICMP protocol was activated to send packets containing error messages, indicating issues contacting the DNS server. The ICMP error response from the DNS server was: “**udp port 53 unreachable**”. Since port 53 is associated with DNS protocol traffic, this indicates an issue with the DNS server. Issues with performing the DNS protocol are further visible because the plus sign after the query identification number `35084` shows flags with the UDP message, and the “**A?**” symbol indicates DNS protocol operations. For this reason, the ICMP error message about port 53 likely indicates that the DNS server was not responding.|

| **Analysis of the data and cause of the incident** | 
|----------------------------------------------------|
| The incident occurred today at 1:24 pm. Customers noticed the company that the webpage wasn’t accessible and was retrieving an error message: “destination port unreachable”. The cybersecurity team is currently investigating the issues so the clients can access the website again. During this investigation, I conducted a packet sniffing test using tcpdump. The resulting data log showed that DNS port 53 was unreachable. The next step is to identify whether the DNS server is down or traffic to port 53 is blocked by the firewall. My observation is that the DNS server might be down due to a successful DoS attack. Further investigation needs to be done to fix any misconfigurations.|

<a href="https://drive.google.com/file/d/1St1BngDaFGIeYRcJ5JfBRqoBvyB9IBwq/view?usp=sharing" target="_blank">
  <img src="https://www.clipartmax.com/png/small/36-360030_pdf-clipart-free-download-clip-building-materials-symbol-pdf.png" alt="LinkedIn Badge" width="24" height="24" />
</a>

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Key Takeaways</p>

<p style="font-size: 12px; font-style: italic; color: #4a4a4a;">
  - Network Traffic Analysis with tcpdump helped me to analyse and visualise DNS and ICMP traffic, making it easy to understand the issue that was affecting the network.
  <br><br>
  - The error returned by the ICMP protocol helped me to detect that the service was blocked, preventing the resolution of the domain plantbasedrecipes.com.
  <br><br>
  - By analysing the tcpdump data packet, I was able to engage in Real-Time Incident Response and identify a possible DoS attack or a misconfiguration in the firewall.
  <br><br>
  - Through this investigation, I enhanced my ability to diagnose network issues, provide clear reports to stakeholders, gained skills in protocol analysis, and learned how to handle DNS server errors in real-world scenarios.
</p>




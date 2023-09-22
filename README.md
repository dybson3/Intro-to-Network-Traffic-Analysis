# Intro-to-Network-Traffic-Analysis
A project implemented on HackTheBox Academy to showcase my skills in tcpdump and Wireshark.

It was impossible to comment everything I have done, for more details [here](https://academy.hackthebox.com/course/preview/intro-to-network-traffic-analysis?gspk=YWRhbWhhbWRhbjYxMjc&gsxid=fnXF79B74i7B&pscd=affiliate.hackthebox.com&utm_campaign={affiliate}).

<br>

**TCPDUMP part I**

**Task 2 - Start a packet capture**

![image](/Screenshots/2.jpg)

Starting capture. This task is a warm-up.

With command "tcpdump -i eth0" I started packet capturing.

<br>

**Task 3 - Basic capture filters**

![image](/Screenshots/3.jpg)

With the command above I utilized basic filtering. In this case it is displaying captured packets in HEX and ASCII.

<br>

**Task 4 - Save capture to .pcap file**

With the usage of command below I saved results to a file called "file.pcap".

![image](/Screenshots/4.jpg)

<br>

**Task 5 - Read a capture from a .pcap file**

![image](/Screenshots/5.jpg)

With this command I was able to read a capture packets from a file saved before.

<br>

**TCPDUMP part II**

**Task 1 - Read a capture from .pcap file without filters implemented**

![image](/Screenshots/6.jpg)

Just a raw .pcap file without filters implemented.

<br>

**Task 2 - Identify the type of traffic seen**

After impelemting some filtering showed on screenshot below, I assumed that there is traffic on port 80 which stands for HTTP connections.

![image](/Screenshots/7.jpg)

<br>

**Task 3 - Interpret the capture in depth**

I was tasked to gather some information such as:

First timestamp:

![image](/Screenshots/8.jpg)

IP address of the host:

![image](/Screenshots/9.jpg)

Type of the protocol used:

![image](/Screenshots/10.jpg)

<br>

**Task 4 - Filter out traffic**

I was given a task to filter out every traffic that is NOT DNS:

![image](/Screenshots/11.jpg)

DNS traffic usually uses UDP protocol on port 53.

<br>

**Task 5 - Filter for tcp traffic**

I was given a task to watch for webservers. On the screenshot below we can see that there is no traffic on port 443 so we don’t have HTTPS connections.

![image](/Screenshots/12.jpg)

<br>
<br>

**WIRESHARK part I**

**Task 1 - Task 1 Select an interface to run a capture**

As before in TCPDUMP a simple warm-up.

![image](/Screenshots/13.jpg)

<br>

**Task 2 - Create a capture filter**

![image](/Screenshots/14.jpg)

Using this command I filtered for traffic only coming through my IP address.

<br>

**WIRESHARK part II**

**Task 1 - Open a pre captured file**

Nothing to show. I just opened a file from HackTheBox resources.

<br>

**Task 2 - Filter the results**

![image](/Screenshots/15.jpg)

In display filter I used a command to fitler for HTTP traffic.

**Task 3 - Follow the stream and extract items found**

This is the most interesting thing in Wireshark for me.

I was tasked to find a server response for client's get request and do right click->follow->tcp stream. 

It is what I received:

![image](/Screenshots/16.jpg)

On the screenshot above I saw that there was a stream of an image. To follow investigation I filtered traffic in Wireshark for images:

![image](/Screenshots/17.jpg)

I extracted jpg files from this traffic and these are the results:

![image](/Screenshots/18.jpg)

<br>

**WIRESHARK part III - Decrypting RDP connections**

**Task 1 - Analyze the traffic included**

I opened a file prepared by HackTheBox.

I instantly filtered for RDP connections:

![image](/Screenshots/19.jpg)

To see more connections I changed the filter from RDP connections for port 3389 that is often used for RDP traffic.

![image](/Screenshots/20.jpg)

It worked. I was able to see more of RDP connections.

<br>

**Task 2 - Provide the RDP-key to Wireshark so it can decrypt the traffic**

![image](/Screenshots/20.jpg)

I added rsa key to the list. The details were provided in lab instruction.

Now while filtering on RDP we see much more traffic:

![image](/Screenshots/21.jpg)

I was given a task to find a username of someone that made this connection.

I found a suspicious packet "Ignored Unknown Record".

![image](/Screenshots/22.jpg)

I found username in the cookie information of this packet

**That's all. Thanks for following to the end! :D**






## 1.Ping

ping command is a network diagnostic tool used to test the connectivity between a local host and a remote host. It sends Internet Control Message Protocol (ICMP) echo request packets to the target host and waits for the ICMP echo reply.

Input

```bash
ping 127.0.0.1
```

Output

```bash
PING 127.0.0.1 (127.0.0.1) 56(84) bytes of data.
64 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.027 ms
64 bytes from 127.0.0.1: icmp_seq=2 ttl=64 time=0.024 ms
64 bytes from 127.0.0.1: icmp_seq=3 ttl=64 time=0.025 ms
^C
--- 127.0.0.1 ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2ms
rtt min/avg/max/mdev = 0.024/0.025/0.027/0.001 ms

```
## 2.Netstat

netstat command is a powerful tool for monitoring and troubleshooting network connections and network interface statistics.

netstat [options]

The most common options used with netstat are:

-a: Display all network connections and listening ports

-n: Display numerical addresses instead of resolving hostnames

-t: Display TCP connections

-u: Display UDP connections

-p: Display the process ID and name associated with each connection

-s: Display networking statistics

## 3.ssh

SH provides encrypted communication between your local machine and the remote server, ensuring the privacy and integrity of your data.

Connect to the remote server and execute a command

```bash
ssh labex@localhost ls -l
```
Connect to the remote server and open an interactive shell

```bash
ssh -t labex@localhost bash
```

Connect to the remote server using a specific SSH port (default is 22)

```bash
ssh -p 2222 labex@localhost
```

## 4.Scp

The scp command is a part of the SSH (Secure Shell) suite of tools and provides a secure way to transfer data over a network. It uses the SSH protocol to encrypt the data during the transfer, ensuring the confidentiality and integrity of the transferred files.
scp [options] source_file_or_directory destination_file_or_directory



```bash
scp ~/project/file.txt labex@remote_host:/home/labex/project/
```

This command will securely copy the file.txt file from the local ~/project directory to the /home/labex/project/ directory on the remote host.

## 5.Curl

Curl is a versatile command-line tool that allows you to interact with web servers, download files, and perform various network-related tasks.

Input

```bash
curl https://curl.se
```

Output

```text
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>curl - transfer data with URL</title>
...
```
Input

```bash
curl -O https://curl.se/download/curl-7.81.0.tar.gz
```

downloading a file from the curl project's website. We'll use the -O option to save the file with the same name as the remote file

## 6.Traceroute

traceroute command sends packets to a destination and displays the route the packets take, along with the time it takes for each hop.

Input 

```bash
traceroute www.example.com
```

Output

```bash
traceroute to www.example.com (93.184.216.34), 30 hops max, 60 byte packets
 1  192.168.1.1 (192.168.1.1)  1.123 ms  1.109 ms  1.095 ms
 2  10.0.0.1 (10.0.0.1)  10.234 ms  10.221 ms  10.208 ms
 3  172.16.0.1 (172.16.0.1)  20.345 ms  20.332 ms  20.319 ms
 4  203.0.113.1 (203.0.113.1)  30.456 ms  30.443 ms  30.430 ms
 5  198.51.100.1 (198.51.100.1)  40.567 ms  40.554 ms  40.541 ms
 6  93.184.216.34 (93.184.216.34)  50.678 ms  50.665 ms  50.652 ms
```
## 7.Nslookup

nslookup command, which is a powerful tool used to query the Domain Name System (DNS) and troubleshoot DNS-related issues.

Input

```bash
nslookup
```
Output

```bash
>
Server:		127.0.0.53
Address:	127.0.0.53#53

>
```
Input 

```bash
nslookup 8.8.8.8
```
Output

```bash
Server:		127.0.0.53
Address:	127.0.0.53#53

Non-authoritative answer:
8.8.8.8.in-addr.arpa	name = dns.google.

```

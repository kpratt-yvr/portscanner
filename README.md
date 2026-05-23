## Port Scanner

A multithreaded TCP port scanner written in Python. Accepts an IP address or domain name and scans a specified range of ports using concurrent threads.

### Usage
```
// python scanner.py [-i <ip> | -d <domain>] [-p <min_port> <max_port>] [-t <threads>]
```

### Arguments 
| Flag  | Long Form | Description  | Default     |
| ------------- | ------------- | ------------- |  ------------- |
| -i | --ip | Target IP address | - | 
| -d | --domain| Target domain name (resolved via DNS) | - | 
| -p | --port | port range: two intergers (max) | - | 
| -t | --thread | number of threads | 4 | 

> -i and -d are mutually exclusive - use one or the other.

### Examples
```
bash
# Scan by IP, ports 20–1000, 8 threads
python scanner.py -i 192.168.1.1 -p 20 1000 -t 8

# Scan by domain, default thread count
python scanner.py -d example.com -p 1 500
```

### Output
```
[+] Port--> 22
[+] Port--> 80
[+] Port--> 443
```
> Press Ctrl + C to stop the scan early

### Requirements
1. Python 3.x
2. Standard library only (socket, threading, queue, argparse) 



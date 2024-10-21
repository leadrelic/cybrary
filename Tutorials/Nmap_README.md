
# Nmap - Network Mapper
Nmap (Network Mapper) is a powerful, open-source tool used for network discovery, security auditing, and vulnerability scanning. It is widely used by network administrators, security professionals, and pentesters.

## Getting Started with Nmap
Before diving into Nmap's functionality, make sure it is installed on your system. You can download and install Nmap from [Nmap's official website](https://nmap.org/download.html).

### Basic Usage
Nmap can be used from the command line with various options for different types of scans and purposes.

#### Scanning a Single Host
To scan a single IP address:
```
nmap 192.168.1.1
```
This will perform a default scan using TCP SYN packets on the target host.

#### Scanning a Range of IP Addresses
You can scan a range of IP addresses as follows:
```
nmap 192.168.1.1-10
```
This command will scan all IP addresses from 192.168.1.1 to 192.168.1.10.

#### Scanning an Entire Subnet
To scan an entire subnet using CIDR notation:
```
nmap 192.168.1.0/24
```
This will scan all 256 IP addresses within the 192.168.1.0/24 subnet.

## Common Scan Types
Nmap supports different types of scans, each with its own advantages and use cases.

### 1. TCP SYN Scan (`-sS`)
The SYN scan is the most popular and efficient scan:
```
nmap -sS 192.168.1.1
```
This scan sends a SYN packet to each port and waits for a response, making it less detectable.

### 2. TCP Connect Scan (`-sT`)
If a SYN scan requires root privileges, you can use the TCP connect scan:
```
nmap -sT 192.168.1.1
```
This scan completes the three-way TCP handshake, making it easier to detect but doesn't require elevated privileges.

### 3. UDP Scan (`-sU`)
To scan UDP ports, which are often used for services like DNS, DHCP, and SNMP:
```
nmap -sU 192.168.1.1
```
UDP scanning is slower than TCP scans due to the nature of the UDP protocol.

### 4. Aggressive Scan (`-A`)
The aggressive scan combines multiple options for a detailed scan:
```
nmap -A 192.168.1.1
```
This enables OS detection, version detection, script scanning, and traceroute.

### 5. Ping Scan (`-sn`)
To check if hosts are up without scanning their ports:
```
nmap -sn 192.168.1.0/24
```
This will only show hosts that respond to ping requests in the specified subnet.

## Advanced Scanning Techniques
Nmap also offers advanced options for more in-depth network analysis.

### 1. OS Detection (`-O`)
Detect the operating system running on the target:
```
nmap -O 192.168.1.1
```
Nmap compares the responses from the target to its database of known OS fingerprints.

### 2. Service Version Detection (`-sV`)
Identify software versions running on open ports:
```
nmap -sV 192.168.1.1
```
This is useful for discovering outdated software with known vulnerabilities.

### 3. Script Scanning (`-sC` or `--script`)
Run Nmap scripts to perform vulnerability scanning:
```
nmap -sC 192.168.1.1
```
Or specify a particular script:
```
nmap --script=http-vuln-cve2017-5638 192.168.1.1
```

## Output Options
You can save scan results using various output formats.

### 1. Normal Output (`-oN`)
```
nmap -oN output.txt 192.168.1.1
```

### 2. XML Output (`-oX`)
```
nmap -oX output.xml 192.168.1.1
```

### 3. Grepable Output (`-oG`)
```
nmap -oG output.gnmap 192.168.1.1
```

### 4. JSON Output (`-oJ`)
```
nmap -oJ output.json 192.168.1.1
```

## Useful Nmap Scripts
Nmap's Scripting Engine (NSE) can be used for detailed scans using built-in scripts.

### Commonly Used NSE Scripts
- `http-enum`: Enumerate directories on a web server.
  ```
  nmap --script=http-enum 192.168.1.1
  ```
- `vuln`: Scan for vulnerabilities.
  ```
  nmap --script=vuln 192.168.1.1
  ```
- `ftp-anon`: Check for anonymous FTP access.
  ```
  nmap --script=ftp-anon 192.168.1.1
  ```

## Further Reading & Resources
- [Official Nmap Documentation](https://nmap.org/book/)
- [Nmap Cheat Sheet](https://github.com/cheat-sheets/nmap)
- [Exploring Nmap Scripting Engine (NSE)](https://nmap.org/nsedoc/)
- [Network Scanning Techniques with Nmap](https://securitytrails.com/blog/nmap)

## Conclusion
Nmap is a versatile tool that every cybersecurity professional should master. This README covers essential Nmap commands and features to get you started. Experiment with different options and explore the vast capabilities of Nmap for network security.

Remember to use Nmap responsibly and only scan networks or devices you have permission to test.

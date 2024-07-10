---

# Nmap Cheat Sheet

This repository provides a comprehensive cheat sheet for using Nmap, a powerful network scanning tool.

### Basic Nmap Scanning
1. **Quick scan for all commonly used ports:**
   ```bash
   nmap -F <target>
   ```

2. **Comprehensive scan for all 65535 ports:**
   ```bash
   nmap -p- <target>
   ```

3. **Scan specific ports:**
   ```bash
   nmap -p <port1,port2,...> <target>
   ```

4. **Scan all ports from 1 to 65535:**
   ```bash
   nmap -p 1-65535 <target>
   ```

### Service Version and OS Detection
1. **Detect service versions running on open ports:**
   ```bash
   nmap -sV <target>
   ```

2. **Detect service versions on specific ports:**
   ```bash
   nmap -sV -p <port1,port2,...> <target>
   ```

3. **Detect the operating system of the target:**
   ```bash
   nmap -O <target>
   ```

### Scanning for Modified SSH Ports
1. **Quick scan for ports commonly used by SSH:**
   ```bash
   nmap -p 22,2222,22222 <target>
   ```

2. **Scan to find possibly modified SSH ports:**
   ```bash
   nmap -p 1-5000 --open -sV --script=ssh-hostkey <target>
   ```
   ```bash
   nmap -p 1-5000 --open -sV <target>
   ```

### Scanning with Additional Options
1. **Scan without pinging first:**
   ```bash
   nmap -Pn <target>
   ```

2. **Scan with more detailed information:**
   ```bash
   nmap -A <target>
   ```

### Example Usage
1. **Finding modified SSH ports:**
   ```bash
   nmap -p 1-5000 -sV --script=ssh-hostkey <target>
   ```
   ```bash
   nmap -p 1-5000 -sV <target>
   ```

2. **Quick scan on all common ports:**
   ```bash
   nmap -F <target>
   ```

3. **Specific scan on ports 22 and 2222:**
   ```bash
   nmap -p 22,2222 <target>
   ```

### Tips
- Replace `<target>` with the IP or hostname of the server you want to scan.
- Use `-v` (verbose) for more detailed output during scanning:
  ```bash
  nmap -v -p- <target>
  ```
- Save the scan results to a file for further analysis:
  ```bash
  nmap -oN output.txt -p 1-65535 <target>
  ```

---

# Pre pivot notes.
This is a work in progress. After taking the OSCP and reading up on the eCPPT I noticed I lacked a great deal in this area.

### Tools
More will be added but for now just a list of tools for proxy and pivoting. 
1. Proxychain<br />
2. Foxyproxy<br />
3. SSH Tunnelling<br />
4. Port Forwarding<br />
5. plink.exe<br />
6. sshuttle<br />

### Flow
1. The first machine should be exploited as normal. More then likely it will be a web vuln and normal priv esc.<br /> 
    1.1 Find a way to get a more stable shell. In the wrath lab on Try Hack Me they had me get the root id_rsa key and then log in using ssh. (Link href to priv esc page)
2. Some quick wins for network discovery.<br /> Linux (arp -a, cat /etc/hosts cat /etc/resolv.config nmcli dev show)<br /> Windows (C:\Windows\System32\drivers\etc\host, ipconfig /all)
3. Set up your tools. Using wget, or curl or scp upload the necessary tools if not already on the box. 
4. #### NMAP Find the active host
    4.1 Command: nmap -T4 IP -vv -sn | grep -v "host down, received no-
response"
5. #### NMAP Find the active ports
    5.1 Command: nmap T4 -p- IP IP -vv OR T4 -p- IP.0/24 -vv 
6. #### Setting up the proxy 
    6.1 Check the Tool descriptions and command sections.<br />
    6.2 From the wrath lab the user used sshuttle<br />
    6.3 Command: sshuttle -r root@10.200.57.200 --ssh-cmd "ssh -i root_key" 10.200.57.0/24 -x 10.200.57.200 

### Resources






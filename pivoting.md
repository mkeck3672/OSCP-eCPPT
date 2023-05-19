# Pre pivot notes.
This is a work in progress. After taking the OSCP and reading up on the eCPPT I noticed I lacked a great deal in this area.

### Tools
<pr> More will be added but for now just a list of tools for proxy and pivoting. 
1. Proxychain<br />
2. Foxyproxy<br />
3. SSH Tunnelling<br />
4. Port Forwarding<br />
5. plink.exe<br />
6. sshuttle<br />

### Flow
1. The first machine should be exploited as normal. More then likely it will be a web vuln and normal priv esc. 
    1.1 Find a way to get a more stable shell. In the wrath lab on Try Hack Me they had me get the root id_rsa key and then log in using ssh. (Link href to priv esc page)
2. Some quick wins for network discovery. Linux (arp -a, cat /etc/hosts cat /etc/resolv.config nmcli dev show) Windows (C:\Windows\System32\drivers\etc\host, ipconfig /all)
3. Set up your tools. Using wget, or curl or scp upload the necessary tools if not already on the box. 
4. #### NMAP 
    4.1 <yl>Command: nmap -T4 <pr>IP</pr> -vv -sn | grep -v "host down, received no-
response"

### Resources






Style
<style>
pr { color: purple   }
yl { color: yellow }
</style>
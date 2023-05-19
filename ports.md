## Port 21 FTP
* Check the ver. and service if avail
    * Example vsftpd 3.0.3 &  FileZilla ftpd 0.9.34 beta
    * Check searchsploit for any exploits
* Check for access
    * Command: ftp IP
    * Check for anonymous login
        * anonymous:anonymous (user:passwd)
* If the user gets access check for file upload and download.
    * Command: wget file.txt
    * Command: put file.txt
* List of nse scripts from nmap - /usr/share/nmap/scripts<br />
ftp-anon.nse<br />
ftp-bounce.nse<br />
ftp-brute.nse<br />
ftp-libopie.nse<br />
ftp-proftpd-backdoor.nse<br />
ftp-syst.nse<br />
ftp-vsftpd-backdoor.nse<br />
ftp-vuln-cve2010-4221.nse<br />
* Brute force ftp creds.
    * Ref: https://null-byte.wonderhowto.com/how-to/brute-force-ftp-credentials-get-server-access-0208763/
### References
1. https://book.hacktricks.xyz/network-services-pentesting/pentesting-ftp
***
## Port 25 SMTP
* Check that port 25 is open
* Check the ver. and service if avail. 
    * Example Postfix smtpd & hMailServer smtpd
* SMTP USER ENUM
    * Ref: https://pentestmonkey.net/tools/user-enumeration/smtp-user-enum
* SMTP BRUTE FORCE USERNAMES
    * Command: sudo smtp-user-enum -M VRFY -U /path/to/file.txt -t IP  
### Exploits
* https://www.exploit-db.com/exploits/34896
* https://www.exploit-db.com/exploits/47984
* https://vk9-sec.com/opensmtpd-6-6-1-remote-code-execution-smtp_mailaddr-cve-2020-7247/
### References
1. https://book.hacktricks.xyz/network-services-pentesting/pentesting-smtp
2. 
***
## Port 80/443/8080.. HTTP
* Run nikto
    * Command: nikto -host http://IP:PORT -output nikto.txt
* Perform forced browsing using feroxbuster
    * Command: feroxbuster -u http://IP:port/ 
    * Feroxbuster has a preinstalled config file for commands this is why there is a lack of commands when using the CLI. 
* Run davtest
    * Command: davtest -url http://IP
* Run cadaver
    * Command: cadaver http://IP  
* NOTE: I have no idea how to use cadaver or davtest more research needs to be done.
* Once the initinal recon is done and if nothing sticks out start treating the attack like a normal pen test.  
* Check Wappalyzer for technologies
* View page source for possible services running. Example: wordpress coldfusion etc.
    * Look for exploits for the services.
* OSINT Check the about pages for employee names and positions. 
* Check for endpoints and parameters via the inspector page. 
* Check session cookies and long strings to decode and possibly modify the values jwt.io, cyberchief.
* Check web vulnerabilities such as SQLi, Path traversal, and file uploads. 
***
### Port 88 KERBEROS
* Run namp kerberos script for user enum
    * Command: Nmap -p 88 --script=krb5-enum-users --script-args krb5-enum-users.realm=’domain’,userdb=/path/to/names.txt IP

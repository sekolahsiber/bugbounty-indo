## Miskonfigurasi Cross Origin Resource Sharing (CORS)

#### Metode 1 (mencari di single target)
```
1. Capture website target dan spider atau crawl semua bagian website menggunakan burp
2. Mencari kata Access-Control pada fitur search burp
3. Coba tambah Origin Header, contoh Origin:attacker.com atau Origin:attacker.target.com atau Origin:target.attacker.com
4. Jika origin ter-refleksikan kembali pada response maka website rentan terhadap CORS
```

#### Metode 2 (Multi target ditambah subdomainnya)
```
1. Cari subdomain dengan tool subfinder, findomain atau sejenisnya dan simpan pada file domains.txt
2. Cek subdomain yang hidup bisa dengan httpx atau httprobe dan simpan pada file alive.txt
3. Kirimkan setiap subdomain ke burp dengan cara (linux)-> cat alive.txt | parallel -j 10 curl --proxy "http://127.0.0.1:8080" -sk 2>/dev/null
4. Ulangin Metode 1
```



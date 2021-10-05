## Cross Site Scripting (XSS)
* XSS adalah kerentanan dimana kita bisa menginject javascript ke dalam web yang dimana web tersebut akan menjalankan apapun script yang kita inject

### Mencari Reflected XSS

1. Menggunakan Burpsuite
```
1. Download plugin Reflection dan Sentinel untuk Burpsuite
2. Jalankan Spider atau crawl website target
3. Cek refleksi pada tab paramater di Burpsuite
4. Kirim sentinalnya atau cek manual
```

2. Menggunakan Waybackurls atau sejenisnya
```
1. Menggunakan Gau atau Waybackurls untuk mendapatkan urls target secara pasif
2. Filter parameter menggunakan grep "=" atau gf patterns dan simpan dalamm file baru
3. Jalankan Gxss atau Bxss pada file tersebut
4. Cek refleksi parameter secara manual atau menggunakan tool seperti dalfox
```

3. Menggunakan Google Dorks
```
1. Menggunakan Google Dork site:target.com dan filter hasilnya
2. Cari paramater dengan menggunakan Google Dork site:target.com inurls:".php?" atau site:target.com filetype:php dan sebagainya
3. Cek apakah isi parameter tersebut ter-refleksi
4. Coba masukkan payload XSS atau kirim ke tool seperti dalfox
```

4. Temukan variabel tersembunyi di Source Code
```
1. Cek file javascript atau sumber kode html untuk menemukan variabel yang tersembunyi atau tidak terpakai
2. Cek manual dengan klik kanan lalu pilih View Page Source dan cari var= atau ="" atau =''
3. Tambahkan variabel tersebut pada url web, contohnya https://target.com?variabelrahasia=xsspayload
```

5. Metode lain
```
1. Gunakan metode 1 atau 2 untuk mengumpulan urls
2. Cari firewall yang digunakan dengan tool whatwaf atau tool lainnya
3. Cari payload yang digunakan untuk bypass (Web App Firewall) WAF di twitter atau sumber lain
4. Serta gunakan tool Arjun untuk mencari parameter tersembunyi
```

6. Tips lain
```
1. Cek halaman error (404,403, dan lain-lain), terkadang terdapat nilai yang ter-refleksikan
2. Coba semua parameter yang me-refleksikan input 
```

### Mencari Stored XSS

* Kebanyakan ditemukan dengan cara manual

Cara Mencari
```
1. Temukan firewall yang dipakai dengan method atau tool di atas dan pilih payload yang cocok untuk melakukan bypass WAF tersebut
2. Input semua field yang bisa di input seperti username, nama, alamat, email, dan sebagainya dengan payload sesuai WAF
3. Coba semua payload XSS pada nama file foto profile atau manapun yang bisa mengupload file
4. Coba disemua komentar di web target
5. Coba semua input yang ter-refleksikan pada halaman yang dimana bisa dilihat orang lain
6. Coba sign-up menggunakan nama ditambah payload XSS
```

### Mencari Blind XSS

* Mirip dengan Reflected XSS atau Stored XSS tetapi tidak ter-refleksikan pada halaman, tetapi kita mendapatkan respon pada server kita

Metode
```
1. Metode yang digunakan sama dengan Reflected dan Stored XSS
2. Gunakan https://xsshunter.com/ atau burpcollabolator atau ngrok untuk servernya
3. Coba pada form kontak atau semacamnya
```

Tips
```
1. Salin semua payload dari xsshunter kita dan tempel ke semua input yang ada
2. XSS hunter juga memiliki payload untuk mem-bypass CSP
3. Buat variasi pada payload (contoh ubah < dengan &alt;)
```

Tempat mencari
```
1. Form review
2. Halaman Contact Us
3. Passwords
4. Alamat
5. Form Nama
6. User-agent
7. Log pengguna
8. Halaman feedback
9. Aplikasi Chat
10. Aplikasi apapun yang memnbutuhkan input pengguna
```

### Mencari DOM XSS

Tips
```
1. Jangan melakukan cara manual
2. Gunakan Scanner Burpsuite PRO
3. Gunakan tool open source
```

## Rate Limit Bypass
 * Rate Limit adalah pembatasan suatu request, contohnya adalah pembatasan percobaan login sebanyak 5 kali jika lebih dari 5 kali maka tidak bisa mencoba lagi, contoh lainnya adalah melakukan percobaan OTP, dan sebagainya

### Teknik Rate Limit Bypass
1. Ubah HTTP Methods nya
```
* Jika request menggunakan metode GET ubah ke PUT, POST, dan lain-lain
* Jika web menggunakan API, coba menggunakan metode HEAD
```

2. Coba masukkan Header berikut ke request
```
X-Forwarded-For: IP
X-Forwarded-IP: IP
X-Client-IP: IP
X-Remote-IP: IP
X-Originating-IP: IP
X-Host: IP
X-Client: IP
```

3. Coba gunakan dua kali X-Forwarded-For
```
X-Forwarded-For:
X-Forwarded-For: IP
```

4. Masukkan HTTP Header untuk menghindari deteksi
```
X-Forwarded: 127.0.0.1
X-Forwarded-By: 127.0.0.1
X-Forwarded-For: 127.0.0.1
X-Forwarded-For-Original: 127.0.0.1
X-Forwarder-For: 127.0.0.1
X-Forward-For: 127.0.0.1
Forwarded-For: 127.0.0.1
Forwarded-For-Ip: 127.0.0.1
X-Custom-IP-Authorization: 127.0.0.1
X-Originating-IP: 127.0.0.1
X-Remote-IP: 127.0.0.1
X-Remote-Addr: 127.0.0.1
```

5. Menggunakan karakter spesial
```
1. Menambahkan Null Byte (%00) di akhir username/email
2. Menambahkan karakter space di akhir usename/email
3. Menambahkan karakter: %0d , %2e , %09 , %20 , %0, %00, %0d%0a, %0a, %0C
4. Menambahkan slash(/) diakhir API endpoint, contohnya example.com/v1/login -> example.com/v1/login
```

6. Menggunakan extensi IP Route burpsuite
```
1. Coba ubah user-agent, cookies, atau apapun yang dapat mengidentifikasi kita
2. Jika terdapat limit 10 kali percobaan setiap IP. maka coba setiap 10 kali percobaan ubah IP yang berada di Header dan coba Header lain
```

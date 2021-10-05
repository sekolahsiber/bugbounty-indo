## Open Redirect
* Open Redirect adalah kerentanan yang dimana penyerang dapat mengarahkan korban ke website yang penyerang mau dimana penyerang bisa mengarahkan korban ke website yang berbahaya

### Trick step by step
```
1. Jika aplikasi mempunyai fitu sign-in atau sign-up, maka daftar sebuah akun dan login
2. Pergi ke halaman profile akun, contoh: target.com/account/profile
3. Salin url halaman profile
4. Logout dan hapus semua cookies dan pergi ke halaman home website target
5. Tempel url yang disalin tadi ke address bar
6. Jika website mengarahkan untuk login, cek address bar nya, kita mungkin menemukan halaman login dengan paramater redirect seperti:
    -> https://target.com/login?next=account/profile
    atau
    -> https://target.com/login?retUrl=account/profile
7. Coba exploit parameternya dengan menambahkan domain luar
    -> https://target.com/login?next=https://evil.com
    atau
    -> https://target.com/login?next=https://target.com@evil.com
8. Jika mengarah ke evil.com maka terdapat kerentanan Open Redirect
9. Coba tambah dampaknya dengan menaikkannya ke XSS
    -> https://target.com/login?next=javascript:alert(1);//
10. Laporkan!!!
```

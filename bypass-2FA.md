## Bypass 2FA

### Bypass 2FA dengan CSRF:-
```
1. Buat 2 akun
2. Nyalakan 2FA pada kedua akun
3. Klik disable 2FA pada salah satu akun dan intercept request dengan burp
4. Buat PoC CSRF dari hasil requestnya
5. Tutup tab untuk akun yang dimatikan 2FA dan tetap login pada akun kedua
6. Buka PoC CSRF pada tab baru
7. Jika 2FA nya disable di akun kedua, maka 2FA sudah ter-bypass
8. Laporkan!!!
```

# Sistem Login E-Perpustakaan

## Daftar File Login

### 1. **index.html** - Halaman Utama (Login Menu)
- Pilihan login Admin atau Siswa
- Design modern dengan gradient background
- Menampilkan fitur masing-masing role

### 2. **indexAdmin.html** - Login Admin
- **Kredensial Demo:**
  - Email: `admin@perpus.id`
  - Password: `admin123`
- Akses ke Panel Administrator

### 3. **loginSiswa.html** - Login Siswa
- Login untuk siswa yang sudah terdaftar
- Fitur Registrasi untuk siswa baru
- Integrasi dengan data siswa di localStorage

---

## Alur Login Siswa

### A. Registrasi Siswa
1. Buka `loginSiswa.html`
2. Klik "Daftar di sini"
3. Masukkan:
   - **NIS**: Nomor Induk Siswa (harus ada di data siswa)
   - **Email**: Email sesuai NIS yang terdaftar
   - **Password**: Minimal 6 karakter
   - **Konfirmasi Password**: Ulangi password
4. Klik "Daftar"

### B. Login Siswa
1. Buka `loginSiswa.html`
2. Masukkan:
   - **Email**: Email yang terdaftar
   - **Password**: Password yang dibuat saat registrasi
3. Klik "Masuk"
4. Jika berhasil, akan diarahkan ke Dashboard Siswa

---

## Data Siswa Default

Sistem sudah menyediakan 2 siswa default yang bisa langsung login:

### Siswa 1 - Ahmad Pratama
- **NIS**: 20230001
- **Email**: ahmad@sekolah.ac.id
- **Password**: password123
- **Jurusan**: Teknik Informatika

### Siswa 2 - Sari Indah
- **NIS**: 20230002
- **Email**: sari.indah@sekolah.ac.id
- **Password**: password123
- **Jurusan**: Sistem Informasi

---

## Fitur-Fitur

### Login Admin
✅ Login dengan kredensial khusus  
✅ Akses ke Dashboard Admin  
✅ Kelola buku, siswa, dan peminjaman  
✅ Logout dengan konfirmasi  

### Login Siswa
✅ Login dengan email dan password  
✅ Registrasi akun baru (jika belum terdaftar)  
✅ Verifikasi NIS dan Email  
✅ Validasi password minimal 6 karakter  
✅ Akses Dashboard Siswa setelah login  
✅ Logout dengan konfirmasi  
✅ Integrasi dengan data siswa di localStorage  

### Keamanan
- Password disimpan di localStorage (untuk demo)
- Session management melalui localStorage
- Validasi email format
- Konfirmasi logout

---

## Struktur localStorage

### Admin Login
```javascript
localStorage.setItem('adminLogin', {
    nama: 'Administrator',
    email: 'admin@perpus.id',
    role: 'Admin'
});
```

### Siswa Login
```javascript
localStorage.setItem('siswaLogin', {
    nama: 'Ahmad Pratama',
    nis: '20230001',
    email: 'ahmad@sekolah.ac.id',
    password: 'password123',
    // ... data siswa lainnya
});
```

---

## Alur Navigasi

```
index.html (Pilihan Login)
├── indexAdmin.html (Login Admin)
│   └── screen/admin/dashboardAdmin.html
│
└── loginSiswa.html (Login Siswa)
    ├── Registrasi Siswa (optional)
    └── screen/user/dashboardUser.html
```

---

## Tips & Catatan

1. **Untuk Testing**: Gunakan email siswa yang sudah ada di data
2. **Registrasi**: NIS dan Email harus sesuai dengan data siswa yang terdaftar
3. **Reset Password**: Hapus browser cache atau gunakan siswa lain
4. **Data Persisten**: Semua data disimpan di localStorage
5. **Logout**: Pastikan untuk logout sebelum berganti user

---

## Troubleshooting

### "Email atau password salah"
- Pastikan email dan password sudah benar
- Gunakan email siswa yang terdaftar
- Cek apakah password sudah didaftarkan sebelumnya

### "NIS tidak terdaftar"
- NIS harus ada di data siswa (Kelola Siswa Admin)
- Hubungi admin untuk menambahkan siswa baru

### "Email tidak sesuai dengan NIS"
- Email harus sama dengan yang terdaftar di admin panel
- Periksa kembali data siswa

---

## Pengembangan Lebih Lanjut

**Fitur yang bisa ditambahkan:**
- 🔐 Hashing password dengan bcrypt
- 📧 Verifikasi email via OTP
- 🔑 Forgot password functionality
- 👤 Profile management siswa
- 📱 Remember me option
- 🔐 Two-factor authentication

---

**Dibuat untuk E-Perpustakaan** | Tahun 2026

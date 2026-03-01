# Minpro1_Pemrograman Berbasis Web

## Nama: Rini Wulandari

## NIM: 2409116048

## Kelas: Sistem Informasi B 2024


# Portofolio Pribadi - Rini Wulandari
## Penjelasan Website
Website portofolio ini saya buat menggunakan HTML, CSS, Bootstrap 5, dan Vue JS untuk menampilkan profil, keterampilan, sertifikat, serta informasi kontak saya. Website ini dirancang dengan tampilan yang sederhana, modern, dan responsif agar nyaman dilihat di berbagai perangkat sekaligus memenuhi ketentuan mini project yang diberikan.

## 1. Navigasi Bar

<img width="1914" height="70" alt="Screenshot 2026-03-01 183102" src="https://github.com/user-attachments/assets/e5c9265d-b066-4b6f-801a-1a8bbc97c324" />

Navigasi bar pada website ini berada di bagian atas halaman dan menggunakan komponen Bootstrap Navbar dengan posisi ```fixed-top```, sehingga tetap terlihat saat pengguna melakukan scroll. Navbar menampilkan nama “Rini Wulandari” di sisi kiri sebagai identitas website, serta menu navigasi di sisi kanan yang terdiri dari Beranda, Tentang Saya, Sertifikat, dan Kontak.

### Penjelasan Kode
HTML
```
<nav class="navbar navbar-expand-lg fixed-top glass-navbar">
  <div class="container">
    
    <a class="navbar-brand fw-bold" href="#">Rini Wulandari</a>

    <button class="navbar-toggler" type="button" 
            data-bs-toggle="collapse" 
            data-bs-target="#navMenu">
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navMenu">
      <ul class="navbar-nav ms-auto nav-spacing">
        <li class="nav-item">
          <a class="nav-link" href="#home">Beranda</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#about">Tentang Saya</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#certificates">Sertifikat</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#contact">Kontak</a>
        </li>
      </ul>
    </div>

  </div>
</nav>
```
- navigasi bar yang responsif menggunakan Bootstrap. Elemen <nav> dengan kelas navbar, navbar-expand-lg, dan fixed-top membuat navbar tetap berada di bagian atas saat halaman di-scroll serta menyesuaikan tampilannya pada berbagai ukuran layar. Kelas tambahan glass-navbar memberikan efek transparan atau blur sesuai desain. Di dalamnya terdapat container agar tata letaknya rapi dan sejajar dengan konten lainnya. Nama “Rini Wulandari” ditampilkan sebagai identitas website melalui navbar-brand, sementara tombol navbar-toggler berfungsi sebagai menu hamburger pada tampilan mobile. Bagian menu navigasi dibuat menggunakan navbar-nav dan diposisikan ke kanan dengan ms-auto, sedangkan setiap nav-link mengarahkan pengguna ke section tertentu dalam halaman seperti Beranda, Tentang Saya, Sertifikat, dan Kontak tanpa perlu berpindah halaman.
```
/* Navigasi */
.glass-navbar{
    background: rgba(255,255,255,0.75);
    backdrop-filter: blur(6px);
    -webkit-backdrop-filter: blur(6px);
    transition: all 0.3s ease;
}

.glass-navbar.scrolled{
    background: rgba(255,255,255,0.9);
    box-shadow: 0 4px 18px rgba(0,0,0,0.08);
}

.nav-link{
  font-weight: 500;
  transition: 0.3s;
}

.nav-link:hover{
  color: black;
}

.nav-spacing .nav-item{
    margin-left: 25px;
}

.nav-link{
    letter-spacing: 0.5px;
    font-weight: 500;
}
```



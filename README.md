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
- Navigasi Bar menggunakan Bootstrap sehingga lebih responsif.
- Elemen ```<nav>``` dengan kelas navbar, ```navbar-expand-lg```, dan ```fixed-top``` membuat navbar tetap berada di bagian atas saat halaman di-scroll serta menyesuaikan tampilannya pada berbagai ukuran layar. Kelas tambahan glass-navbar memberikan efek transparan atau blur sesuai desain. Di dalamnya terdapat container agar tata letaknya rapi dan sejajar dengan konten lainnya. Nama “Rini Wulandari” ditampilkan sebagai identitas website melalui ```navbar-brand```, sementara tombol ```navbar-toggler``` berfungsi sebagai menu hamburger pada tampilan mobile. Bagian menu navigasi dibuat menggunakan ```navbar-nav``` dan diposisikan ke kanan dengan ```ms-auto```, sedangkan setiap ```nav-link``` mengarahkan pengguna ke section tertentu dalam halaman seperti Beranda, Tentang Saya, Sertifikat, dan Kontak tanpa perlu berpindah halaman.


CSS
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
- ```.glass-navbar``` → Membuat navbar transparan dengan efek blur agar terlihat modern dan elegan.
- ```.glass-navbar.scrolled``` → Mengubah tampilan navbar saat di-scroll menjadi lebih solid dan diberi bayangan agar lebih jelas.
- ```.nav-link``` → Mengatur tampilan teks menu (ketebalan huruf dan efek transisi).
- ```.nav-link:hover``` → Mengubah warna teks menjadi hitam saat kursor diarahkan ke menu.
- ```.nav-spacing``` ```.nav-item``` → Memberikan jarak antar menu agar tidak terlalu rapat.
- ```letter-spacing``` pada ```.nav-link``` → Memberi sedikit jarak antar huruf agar tampilan lebih rapi dan nyaman dibaca.


## 2. Beranda

<img width="1897" height="1021" alt="Screenshot 2026-03-01 191802" src="https://github.com/user-attachments/assets/f76096bf-489c-439f-a7f2-37313d1408fc" />

Berisi:
1. Foto Profil
2. Pengenalan Nama dan Deskripsi singkat.

### Penjelasan Kode
HTML
```
<!-- Beranda -->
<section id="home" class="hero-section">
  <div class="container">
    <div class="row align-items-center gx-2">

      <div class="col-md-5 mb-5 mb-md-0 text-center text-md-start">
        <h5>Perkenalkan, Saya</h5>
        <h1 class="fw-bold display-5">{{ name }}</h1>
        <p class="text-muted">{{ description }}</p>
        <a href="#about" class="btn btn-dark rounded-pill px-4">
          Tentang Saya
        </a>
      </div>

      <div class="col-md-7 text-center hero-image-wrapper">
        <img src="images/Profil1_.jpg" class="hero-image">
      </div>

    </div>
  </div>
</section>
```
```
createApp({
  data(){
    return{

      name:"Rini Wulandari",
      description:"Mahasiswi Aktif S1 Sistem Informasi Fakultas Teknik Universitas Mulawarman.",

      about:{
        title:"Latar Belakang",
        image:"images/Profil2.jpg",
        description:"Saya adalah mahasiswa Sistem Informasi Universitas Mulawarman dengan minat pada pengelolaan dan pengolahan data, khususnya di bidang database. Saat ini saya sedang mendalami konsep perancangan dan manajemen basis data untuk mendukung pengembangan sistem informasi yang efektif. Selain itu, saya terbiasa menggunakan Microsoft Word, Microsoft Excel, dan Canva untuk kebutuhan akademik maupun organisasi, serta didukung dengan kemampuan komunikasi dan public speaking yang baik."
      },
```
- Beranda (hero section) sebagai tampilan awal website.
- Di dalamnya terdapat teks perkenalan, nama yang ditampilkan secara dinamis menggunakan Vue ```({{ name }})```, serta deskripsi singkat ```({{ description }})```. Tombol “Tentang Saya” berfungsi untuk mengarahkan pengguna ke bagian profil.
- Layout dibuat dua kolom menggunakan Bootstrap agar teks berada di kiri dan foto profil di kanan, sehingga tampilannya terlihat rapi, seimbang, dan responsif di berbagai ukuran layar.

CSS
```
.hero-section{
    min-height: 100vh;
    padding-top: 120px;
    display: flex;
    align-items: center;
}

.hero-section .col-md-5{
    padding-right: 10px;
}

.hero-section .col-md-7{
    padding-left: 10px;
}

.hero-image-wrapper{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
}

.hero-image{
    width: 100%;
    max-width: 480px; 
    aspect-ratio: 1/1;
    object-fit: cover;
    object-position: center 23%;

    border-radius: 50%;
    border: 6px solid white;

    box-shadow: 0 20px 40px rgba(0,0,0,0.15);
    transition: 0.4s ease;
    z-index: 2;
}

.hero-image:hover{
    transform: scale(1.05);
}

.hero-image-wrapper::before{
    content: "";
    position: absolute;
    width: 120%;
    height: 120%;
    background: radial-gradient(circle, rgba(147,197,253,0.3), transparent 70%);
    border-radius: 50%;
    z-index: 1;
    filter: blur(20px);
}

@media (max-width: 768px){

    .hero-section{
        padding-top: 100px;
        text-align: center;
    }

    .hero-image{
        max-width: 260px;
    }

}

.section-space{
padding:100px 0;
}
```
- ```.hero-section``` → Mengatur tinggi section memenuhi layar (100vh), memberi jarak dari atas, dan membuat konten rata tengah secara vertikal.
- ```.col-md-5 & .col-md-7``` → Menyesuaikan jarak antara teks dan gambar agar lebih rapat dan proporsional.
- ```.hero-image-wrapper``` → Mengatur posisi gambar agar berada di tengah dan memungkinkan penambahan efek latar belakang.
- ```.hero-image``` → Mengatur ukuran foto, membuatnya berbentuk lingkaran, menambahkan border putih, bayangan, serta efek zoom saat hover.
- ```.hero-image-wrapper::before``` → Menambahkan efek glow atau cahaya lembut di belakang foto agar terlihat lebih menarik.
- ```@media (max-width: 768px)``` → Mengatur tampilan agar tetap responsif di layar kecil dengan mengecilkan ukuran gambar dan menyesuaikan jarak.
- ```.section-space``` → Memberikan jarak atas dan bawah pada setiap section agar tampilan lebih lega dan rapi.


## 3. Tentang Saya

<img width="1900" height="1025" alt="Screenshot 2026-03-01 194530" src="https://github.com/user-attachments/assets/bd833d60-0785-433c-9aa9-24401763d92e" />

Berisi:
1. Latar Belakang
2. Skill
3. Pengalaman

### Penjelasan Kode
HTML
```
<!-- Tentang Saya -->
<section id="about" class="about-section">
  <div class="container">

    <div class="text-center mb-5">
      <h2 class="fw-bold">Tentang Saya</h2>
    </div>

    <div class="row g-4 align-items-stretch">

      <!-- Latar Belakang -->
      <div class="col-md-6">
        <div class="about-card h-100 p-4 text-center">

          <img :src="about.image" class="about-image mb-4">

          <h4 class="fw-bold mb-3">{{ about.title }}</h4>

          <p class="text-muted">
            {{ about.description }}
          </p>

        </div>
      </div>

      <div class="col-md-6">
        <div class="row g-4 h-100">

          <!-- Skill -->
          <div class="col-12">
            <div class="about-card right-card p-4">

              <h5 class="fw-bold mb-2">Skill</h5>
              <div class="accent-line mb-4"></div>

              <div v-for="skill in skills" class="mb-3">

                <div class="d-flex justify-content-between">
                  <span>{{ skill.name }}</span>
                  <span>{{ skill.level }}%</span>
                </div>

                <div class="progress">
                  <div class="progress-bar skill-bar"
                       :style="{ width: skill.level + '%' }">
                  </div>
                </div>

              </div>

            </div>
          </div>

          <!-- Pengalaman -->
          <div class="col-12">
            <div class="about-card right-card p-4">

              <h5 class="fw-bold mb-2">Pengalaman</h5>
              <div class="accent-line mb-3"></div>

              <p class="text-muted mb-0">
                {{ experience }}
              </p>

            </div>
          </div>

        </div>
      </div>

    </div>

  </div>
</section>
```
```
      about:{
        title:"Latar Belakang",
        image:"images/Profil2.jpg",
        description:"Saya adalah mahasiswa Sistem Informasi Universitas Mulawarman dengan minat pada pengelolaan dan pengolahan data, khususnya di bidang database. Saat ini saya sedang mendalami konsep perancangan dan manajemen basis data untuk mendukung pengembangan sistem informasi yang efektif. Selain itu, saya terbiasa menggunakan Microsoft Word, Microsoft Excel, dan Canva untuk kebutuhan akademik maupun organisasi, serta didukung dengan kemampuan komunikasi dan public speaking yang baik."
      },

      skills:[
        {name:"Microsoft Word", level:90},
        {name:"Microsoft Excel", level:85},
        {name:"Database", level:75},
        {name:"Public Speaking", level:90}
      ],

      experience:"Sejauh ini telah mengembangkan soft skill yang diinginkan dan pada tahun 2025 saat Kepengurusan INFORSA 2025 telah berpartisipasi aktif dalam kegiatan program kerja. Akademik juga menjadi yang paling utama dan telah mengerjakan beberapa project mata kuliah maupun praktikum.",
```
- Tentang Saya secara dinamis menggunakan Vue.js.
- Bagian kiri menampilkan latar belakang yang berisi gambar, judul, dan deskripsi yang diambil dari objek ```about```, sehingga isinya bisa diubah langsung dari data tanpa mengedit HTML.
- Di sisi kanan terdapat dua card, yaitu Skill dan Pengalaman. Data skill ditampilkan menggunakan ```v-for``` untuk melakukan perulangan array ```skills```, lalu level kemampuannya divisualisasikan dalam bentuk progress bar yang lebarnya menyesuaikan persentase. Sementara itu, bagian pengalaman mengambil teks dari variabel ```experience```.

CSS
```
/* Tentang Saya */
.about-section{
    padding: 100px 0;
    background: #f9fafb;
}

.about-card{
    background: white;
    border-radius: 25px;
    box-shadow: 0 15px 35px rgba(0,0,0,0.06);
    transition: 0.3s ease;
}

.about-card:hover{
    transform: translateY(-8px);
    box-shadow: 0 20px 45px rgba(0,0,0,0.1);
}

.about-image{
    width: 100%;
    max-width: 250px;
    border-radius: 15px;
    object-fit: cover;
    box-shadow: 0 10px 25px rgba(0,0,0,0.1);
}

.accent-line{
    width: 40px;
    height: 3px;
    background: #1f2937;
    border-radius: 5px;
}
```
- ```.about-section``` → Memberikan jarak atas-bawah (padding) dan warna background terang agar section terlihat bersih dan lega.
- ```.about-card``` → Membuat tampilan card berwarna putih dengan sudut membulat dan bayangan halus supaya terlihat modern.
- ```.about-card:hover``` → Memberikan efek naik sedikit dan bayangan lebih tegas saat kursor diarahkan ke card.
- ```.about-image``` → Mengatur ukuran gambar agar proporsional, sudutnya membulat, dan diberi bayangan agar lebih menarik.
- ```.accent-line``` → Membuat garis kecil sebagai elemen dekoratif untuk mempertegas judul di dalam card.










































<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.5">
  <title>Hanifah · Portfolio</title>
  <!-- Font & Icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    /* ========== RESET & VARIABLES ========== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --primary: #5a6c7e;
      --secondary: #9aaec2;
      --accent: #c4d3df;
      --light: #f8faff;
      --dark: #1e2a36;
      --card-bg: #ffffff;
      --shadow: 0 20px 40px -12px rgba(0, 20, 30, 0.12);
      --radius: 24px;
      --transition: 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
      --font: 'Poppins', sans-serif;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: var(--font);
      background-color: var(--light);
      color: var(--dark);
      line-height: 1.6;
      overflow-x: hidden;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    img {
      max-width: 100%;
      display: block;
      height: auto;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* ========== UTILITY ========== */
    .section-title {
      font-size: 2.2rem;
      font-weight: 700;
      margin-bottom: 2.5rem;
      position: relative;
      display: inline-block;
      letter-spacing: -0.5px;
    }
    .section-title::after {
      content: '';
      position: absolute;
      bottom: -8px;
      left: 0;
      width: 60px;
      height: 4px;
      background: var(--secondary);
      border-radius: 8px;
    }

    .fade-in {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.8s ease, transform 0.8s ease;
    }
    .fade-in.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ========== NAVBAR ========== */
    .navbar {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 999;
      background: rgba(255, 255, 255, 0.75);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      box-shadow: 0 4px 20px rgba(0,0,0,0.03);
      padding: 14px 0;
      transition: var(--transition);
    }
    .navbar .container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
    }
    .nav-logo {
      font-weight: 700;
      font-size: 1.5rem;
      color: var(--dark);
      letter-spacing: -0.5px;
    }
    .nav-logo span {
      color: var(--primary);
    }

    .nav-menu {
      display: flex;
      gap: 28px;
      list-style: none;
      font-weight: 500;
      font-size: 0.95rem;
    }
    .nav-menu a {
      padding: 6px 0;
      border-bottom: 2px solid transparent;
      transition: var(--transition);
      color: var(--dark);
    }
    .nav-menu a:hover,
    .nav-menu a.active {
      border-bottom-color: var(--primary);
      color: var(--primary);
    }

    /* hamburger */
    .hamburger {
      display: none;
      flex-direction: column;
      gap: 5px;
      cursor: pointer;
      background: none;
      border: none;
      padding: 6px;
    }
    .hamburger span {
      display: block;
      width: 28px;
      height: 3px;
      background: var(--dark);
      border-radius: 6px;
      transition: var(--transition);
    }

    /* ========== HERO / HOME ========== */
    #home {
      padding-top: 120px;
      padding-bottom: 70px;
      min-height: 100vh;
      display: flex;
      align-items: center;
    }
    .hero-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 50px;
      align-items: center;
    }
    .hero-content h1 {
      font-size: 3.8rem;
      font-weight: 800;
      line-height: 1.1;
      letter-spacing: -1px;
    }
    .hero-content h1 span {
      color: var(--primary);
    }
    .hero-sub {
      font-size: 1.3rem;
      font-weight: 400;
      color: var(--primary);
      margin-top: 6px;
    }
    .hero-badge {
      display: flex;
      flex-wrap: wrap;
      gap: 12px 28px;
      margin: 24px 0 18px;
      font-size: 1rem;
    }
    .hero-badge i {
      color: var(--primary);
      margin-right: 8px;
      width: 20px;
    }
    .hero-motto {
      font-size: 1.5rem;
      font-weight: 300;
      font-style: italic;
      color: var(--secondary);
      border-left: 4px solid var(--accent);
      padding-left: 20px;
      margin: 20px 0 28px;
    }
    .btn-group {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
    }
    .btn {
      display: inline-block;
      padding: 12px 32px;
      border-radius: 60px;
      font-weight: 600;
      background: var(--card-bg);
      box-shadow: var(--shadow);
      border: 1px solid rgba(90, 108, 126, 0.15);
      transition: var(--transition);
      cursor: pointer;
      font-size: 0.95rem;
    }
    .btn-primary {
      background: var(--primary);
      color: white;
      border: none;
    }
    .btn-primary:hover {
      background: #3d4f60;
      transform: translateY(-3px);
      box-shadow: 0 16px 30px -8px rgba(90, 108, 126, 0.3);
    }
    .btn-outline:hover {
      background: var(--primary);
      color: white;
      border-color: var(--primary);
      transform: translateY(-3px);
    }
    .hero-image {
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .profile-img {
      width: 320px;
      height: 320px;
      border-radius: 50%;
      object-fit: cover;
      box-shadow: 0 30px 50px -20px rgba(0,0,0,0.2);
      border: 6px solid white;
      background: #d9e2ec;
    }
    /* placeholder color */
    .profile-img[src=""] {
      background: linear-gradient(145deg, #d9e2ec, #c4d3df);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--primary);
      font-weight: 500;
    }

    /* ========== TENTANG SAYA ========== */
    #tentang {
      padding: 80px 0;
      background: white;
    }
    .about-grid {
      display: grid;
      grid-template-columns: 200px 1fr;
      gap: 40px;
      align-items: start;
    }
    .about-img {
      width: 200px;
      height: 200px;
      border-radius: 30px;
      object-fit: cover;
      background: #d9e2ec;
      box-shadow: var(--shadow);
    }
    .about-text p {
      margin-bottom: 18px;
      font-size: 1.05rem;
      color: #2d3b47;
    }
    .chip-group {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 20px;
    }
    .chip {
      background: var(--accent);
      padding: 8px 22px;
      border-radius: 60px;
      font-weight: 500;
      font-size: 0.9rem;
      color: var(--dark);
      transition: var(--transition);
    }
    .chip:hover {
      background: var(--primary);
      color: white;
      transform: scale(1.03);
    }

    /* ========== CV ========== */
    #cv {
      padding: 80px 0;
      background: var(--light);
    }
    .cv-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 40px;
    }
    .cv-card {
      background: white;
      padding: 30px 28px;
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      transition: var(--transition);
    }
    .cv-card:hover {
      transform: translateY(-6px);
      box-shadow: 0 30px 50px -18px rgba(0,0,0,0.12);
    }
    .cv-card h3 {
      font-size: 1.4rem;
      font-weight: 600;
      margin-bottom: 20px;
      display: flex;
      align-items: center;
      gap: 12px;
    }
    .cv-card h3 i {
      color: var(--primary);
    }
    .cv-timeline {
      list-style: none;
      padding-left: 6px;
    }
    .cv-timeline li {
      padding: 8px 0 8px 24px;
      border-left: 3px solid var(--accent);
      margin-left: 8px;
      position: relative;
    }
    .cv-timeline li::before {
      content: '';
      position: absolute;
      left: -7px;
      top: 14px;
      width: 12px;
      height: 12px;
      border-radius: 50%;
      background: var(--primary);
      border: 2px solid white;
    }
    .cv-timeline li span {
      font-weight: 500;
    }
    .cv-detail {
      margin: 10px 0 6px;
      color: #2d3b47;
    }

    /* ========== KARYA & GALERI ========== */
    #karya, #galeri {
      padding: 80px 0;
    }
    #galeri {
      background: white;
    }
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 24px;
    }
    .gallery-item {
      border-radius: 20px;
      overflow: hidden;
      box-shadow: var(--shadow);
      transition: var(--transition);
      cursor: pointer;
      background: #d9e2ec;
      position: relative;
    }
    .gallery-item img {
      width: 100%;
      height: 220px;
      object-fit: cover;
      transition: var(--transition);
      background: #d9e2ec;
    }
    .gallery-item:hover {
      transform: scale(1.02);
      box-shadow: 0 24px 40px -16px rgba(0,0,0,0.2);
    }
    .gallery-item:hover img {
      transform: scale(1.04);
    }
    .gallery-label {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      padding: 12px;
      background: linear-gradient(transparent, rgba(0,0,0,0.4));
      color: white;
      font-weight: 500;
      font-size: 0.9rem;
      backdrop-filter: blur(4px);
    }

    /* masonry style for galeri */
    .masonry-grid {
      column-count: 3;
      column-gap: 20px;
    }
    .masonry-grid .gallery-item {
      break-inside: avoid;
      margin-bottom: 20px;
    }
    .masonry-grid .gallery-item img {
      height: auto;
      aspect-ratio: 1 / 1;
    }

    /* ========== MEDSOS ========== */
    #medsos {
      padding: 80px 0;
      background: var(--light);
    }
    .medsos-card {
      max-width: 480px;
      margin: 0 auto;
      background: white;
      padding: 40px 32px;
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      text-align: center;
    }
    .medsos-card i {
      font-size: 2.6rem;
      color: var(--primary);
      margin-bottom: 10px;
    }
    .medsos-card h3 {
      font-size: 1.8rem;
      font-weight: 600;
    }
    .medsos-card .username {
      color: var(--secondary);
      font-weight: 500;
      margin: 8px 0 24px;
    }

    /* ========== KONTAK ========== */
    #kontak {
      padding: 80px 0;
      background: white;
    }
    .kontak-card {
      max-width: 500px;
      margin: 0 auto;
      background: var(--light);
      padding: 40px;
      border-radius: var(--radius);
      text-align: center;
      box-shadow: var(--shadow);
    }
    .kontak-card i {
      font-size: 2.8rem;
      color: var(--primary);
    }
    .kontak-card .phone {
      font-size: 2rem;
      font-weight: 600;
      margin: 12px 0 20px;
    }

    /* ========== TESTIMONI ========== */
    #testimoni {
      padding: 80px 0;
      background: var(--light);
    }
    .testi-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
      gap: 30px;
    }
    .testi-card {
      background: white;
      padding: 30px 24px;
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      transition: var(--transition);
      text-align: center;
    }
    .testi-card:hover {
      transform: translateY(-6px);
    }
    .testi-card i {
      color: var(--secondary);
      font-size: 2rem;
      opacity: 0.3;
      margin-bottom: 8px;
    }
    .testi-card p {
      font-style: italic;
      color: #2d3b47;
    }
    .testi-card .name {
      font-weight: 600;
      margin-top: 14px;
      color: var(--primary);
    }

    /* ========== FOOTER ========== */
    footer {
      background: var(--dark);
      color: #cfdde8;
      padding: 40px 0 24px;
      text-align: center;
    }
    footer .motto {
      font-style: italic;
      font-weight: 300;
      margin: 6px 0 12px;
    }
    .back-top {
      display: inline-block;
      margin-top: 16px;
      background: var(--primary);
      color: white;
      width: 44px;
      height: 44px;
      border-radius: 60px;
      line-height: 44px;
      font-size: 1.2rem;
      transition: var(--transition);
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
    }
    .back-top:hover {
      transform: translateY(-4px);
      background: #3d4f60;
    }

    /* ========== LIGHTBOX ========== */
    .lightbox {
      display: none;
      position: fixed;
      top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(0,0,0,0.7);
      backdrop-filter: blur(6px);
      z-index: 9999;
      justify-content: center;
      align-items: center;
    }
    .lightbox.active {
      display: flex;
    }
    .lightbox img {
      max-width: 80%;
      max-height: 80%;
      border-radius: 16px;
      box-shadow: 0 40px 80px rgba(0,0,0,0.5);
    }
    .lightbox-close {
      position: absolute;
      top: 30px;
      right: 40px;
      color: white;
      font-size: 2.8rem;
      cursor: pointer;
      transition: var(--transition);
    }
    .lightbox-close:hover {
      transform: rotate(90deg);
    }

    /* ========== RESPONSIVE ========== */
    @media (max-width: 992px) {
      .hero-grid {
        grid-template-columns: 1fr;
        text-align: center;
      }
      .hero-image {
        order: -1;
      }
      .profile-img {
        width: 220px;
        height: 220px;
      }
      .about-grid {
        grid-template-columns: 1fr;
        text-align: center;
      }
      .about-img {
        margin: 0 auto;
        width: 160px;
        height: 160px;
      }
      .cv-grid {
        grid-template-columns: 1fr;
      }
      .masonry-grid {
        column-count: 2;
      }
    }

    @media (max-width: 768px) {
      .nav-menu {
        display: none;
        flex-direction: column;
        gap: 12px;
        width: 100%;
        background: white;
        padding: 24px 20px;
        border-radius: 20px;
        box-shadow: var(--shadow);
        margin-top: 12px;
      }
      .nav-menu.active {
        display: flex;
      }
      .hamburger {
        display: flex;
      }
      .hero-content h1 {
        font-size: 2.8rem;
      }
      .section-title {
        font-size: 1.8rem;
      }
      .btn-group {
        justify-content: center;
      }
      .masonry-grid {
        column-count: 2;
      }
      .gallery-grid {
        grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
      }
    }

    @media (max-width: 480px) {
      .container { padding: 0 16px; }
      .hero-content h1 { font-size: 2.2rem; }
      .profile-img { width: 170px; height: 170px; }
      .masonry-grid { column-count: 1; }
      .gallery-grid { grid-template-columns: 1fr 1fr; }
      .gallery-item img { height: 140px; }
    }
  </style>
</head>
<body>
  <!-- NAVBAR -->
  <nav class="navbar" id="navbar">
    <div class="container">
      <div class="nav-logo">Hanifah<span>.</span></div>
      <button class="hamburger" id="hamburger" aria-label="Menu navigasi">
        <span></span><span></span><span></span>
      </button>
      <ul class="nav-menu" id="navMenu">
        <li><a href="#home" class="active">Home</a></li>
        <li><a href="#tentang">Tentang</a></li>
        <li><a href="#cv">CV</a></li>
        <li><a href="#karya">Karya</a></li>
        <li><a href="#galeri">Galeri</a></li>
        <li><a href="#medsos">Media Sosial</a></li>
        <li><a href="#kontak">Kontak</a></li>
        <li><a href="#testimoni">Testimoni</a></li>
      </ul>
    </div>
  </nav>

  <!-- LIGHTBOX -->
  <div class="lightbox" id="lightbox">
    <span class="lightbox-close" id="lightboxClose">&times;</span>
    <img src="" alt="Foto diperbesar" id="lightboxImg">
  </div>

  <!-- HOME -->
  <section id="home">
    <div class="container hero-grid">
      <div class="hero-content fade-in">
        <h1>Hanifah</h1>
        <div class="hero-sub">Pelajar SMK 42 Jakarta · Broadcasting</div>
        <div class="hero-badge">
          <span><i class="fas fa-graduation-cap"></i> SMK 42 Jakarta</span>
          <span><i class="fas fa-music"></i> Bermain Gitar</span>
          <span><i class="fas fa-film"></i> Sutradara Film</span>
        </div>
        <div class="hero-motto">"Be yourself, and keep growing."</div>
        <div class="btn-group">
          <a href="#tentang" class="btn btn-primary">Tentang Saya</a>
          <a href="#cv" class="btn btn-outline">Lihat CV</a>
          <a href="#" class="btn btn-outline" id="downloadCvBtn"><i class="fas fa-download"></i> Download CV</a>
        </div>
      </div>
      <div class="hero-image fade-in">
        <!-- Ganti dengan foto profil: images/profile.jpg -->
        <img src="" alt="Foto Profil Hanifah" class="profile-img" id="profileImg" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 200 200%22%3E%3Crect width=%22200%22 height=%22200%22 fill=%22%23d9e2ec%22/%3E%3Ctext x=%2250%22 y=%22115%22 font-family=%22Poppins%22 font-size=%2220%22 fill=%22%235a6c7e%22%3EFoto%3C/text%3E%3C/svg%3E'">
      </div>
    </div>
  </section>

  <!-- TENTANG -->
  <section id="tentang">
    <div class="container">
      <h2 class="section-title fade-in">Tentang Saya</h2>
      <div class="about-grid">
        <!-- Ganti dengan foto profil kedua -->
        <img src="" alt="Foto Hanifah" class="about-img fade-in" id="aboutImg" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 200 200%22%3E%3Crect width=%22200%22 height=%22200%22 fill=%22%23d9e2ec%22/%3E%3Ctext x=%2250%22 y=%22115%22 font-family=%22Poppins%22 font-size=%2220%22 fill=%22%235a6c7e%22%3EFoto%3C/text%3E%3C/svg%3E'">
        <div class="about-text fade-in">
          <p>Halo! Saya adalah seorang pelajar yang memiliki semangat untuk belajar, berkembang, dan mencoba hal-hal baru. Saya tertarik pada dunia kreativitas, teknologi, serta berbagai kegiatan yang dapat menambah pengalaman dan keterampilan.</p>
          <p>Saya merupakan pribadi yang bertanggung jawab, mau bekerja sama dengan orang lain, dan berusaha menyelesaikan setiap tugas dengan sebaik mungkin. Saya percaya bahwa setiap pengalaman adalah kesempatan untuk belajar dan menjadi pribadi yang lebih baik.</p>
          <p>Ke depannya, saya ingin terus mengembangkan kemampuan, mendapatkan pengalaman baru, serta menghasilkan karya yang bermanfaat dan membanggakan.</p>
          <div class="chip-group">
            <span class="chip">Kreatif</span>
            <span class="chip">Bertanggung Jawab</span>
            <span class="chip">Mau Belajar</span>
            <span class="chip">Teamwork</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- CV -->
  <section id="cv">
    <div class="container">
      <h2 class="section-title fade-in">Curriculum Vitae</h2>
      <div class="cv-grid">
        <div class="cv-card fade-in">
          <h3><i class="fas fa-user-circle"></i> Data Diri</h3>
          <p><strong>Nama:</strong> Hanifah</p>
          <p><strong>Jurusan:</strong> Broadcasting</p>
          <p><strong>Sekolah:</strong> SMK 42 Jakarta</p>
          <p><strong>Cita-cita:</strong> Menjadi Sutradara Film</p>
        </div>
        <div class="cv-card fade-in">
          <h3><i class="fas fa-school"></i> Riwayat Pendidikan</h3>
          <ul class="cv-timeline">
            <li><span>TK</span> <span class="cv-detail">(placeholder)</span></li>
            <li><span>SD</span> <span class="cv-detail">(placeholder)</span></li>
            <li><span>SMP</span> <span class="cv-detail">(placeholder)</span></li>
            <li><span>SMK 42 Jakarta</span> <span class="cv-detail">— Jurusan Broadcasting</span></li>
          </ul>
        </div>
        <div class="cv-card fade-in">
          <h3><i class="fas fa-users"></i> Pengalaman Organisasi</h3>
          <p><strong>OSIS</strong></p>
          <ul style="list-style:disc; padding-left:20px; color:#2d3b47;">
            <li>Aktif dalam organisasi OSIS.</li>
            <li>Pernah menjadi Ketua Sekbid.</li>
            <li>Memiliki pengalaman bekerja sama dalam menjalankan kegiatan organisasi.</li>
          </ul>
        </div>
        <div class="cv-card fade-in">
          <h3><i class="fas fa-palette"></i> Kegiatan / Ekstrakurikuler</h3>
          <p><strong>Ratoh Jaroe</strong></p>
          <ul style="list-style:disc; padding-left:20px; color:#2d3b47;">
            <li>Mengikuti kegiatan ekstrakurikuler Ratoh Jaroe.</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- KARYA -->
  <section id="karya">
    <div class="container">
      <h2 class="section-title fade-in">Hasil Karya</h2>
      <div class="gallery-grid" id="karyaGrid">
        <!-- Ganti src dengan images/karya1.jpg ... -->
        <div class="gallery-item fade-in"><img src="" alt="Karya 1" data-src="placeholder" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 300 300%22%3E%3Crect width=%22300%22 height=%22300%22 fill=%22%23c4d3df%22/%3E%3Ctext x=%2280%22 y=%22160%22 font-family=%22Poppins%22 font-size=%2230%22 fill=%22%235a6c7e%22%3EKarya 1%3C/text%3E%3C/svg%3E'"><div class="gallery-label">Karya 1</div></div>
        <div class="gallery-item fade-in"><img src="" alt="Karya 2" data-src="placeholder" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 300 300%22%3E%3Crect width=%22300%22 height=%22300%22 fill=%22%23c4d3df%22/%3E%3Ctext x=%2280%22 y=%22160%22 font-family=%22Poppins%22 font-size=%2230%22 fill=%22%235a6c7e%22%3EKarya 2%3C/text%3E%3C/svg%3E'"><div class="gallery-label">Karya 2</div></div>
        <div class="gallery-item fade-in"><img src="" alt="Karya 3" data-src="placeholder" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 300 300%22%3E%3Crect width=%22300%22 height=%22300%22 fill=%22%23c4d3df%22/%3E%3Ctext x=%2280%22 y=%22160%22 font-family=%22Poppins%22 font-size=%2230%22 fill=%22%235a6c7e%22%3EKarya 3%3C/text%3E%3C/svg%3E'"><div class="gallery-label">Karya 3</div></div>
        <div class="gallery-item fade-in"><img src="" alt="Karya 4" data-src="placeholder" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 300 300%22%3E%3Crect width=%22300%22 height=%22300%22 fill=%22%23c4d3df%22/%3E%3Ctext x=%2280%22 y=%22160%22 font-family=%22Poppins%22 font-size=%2230%22 fill=%22%235a6c7e%22%3EKarya 4%3C/text%3E%3C/svg%3E'"><div class="gallery-label">Karya 4</div></div>
        <div class="gallery-item fade-in"><img src="" alt="Karya 5" data-src="placeholder" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 300 300%22%3E%3Crect width=%22300%22 height=%22300%22 fill=%22%23c4d3df%22/%3E%3Ctext x=%2280%22 y=%22160%22 font-family=%22Poppins%22 font-size=%2230%22 fill=%22%235a6c7e%22%3EKarya 5%3C/text%3E%3C/svg%3E'"><div class="gallery-label">Karya 5</div></div>
        <div class="gallery-item fade-in"><img src="" alt="Karya 6" data-src="placeholder" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 300 300%22%3E%3Crect width=%22300%22 height=%22300%22 fill=%22%23c4d3df%22/%3E%3Ctext x=%2280%22 y=%22160%22 font-family=%22Poppins%22 font-size=%2230%22 fill=%22%235a6c7e%22%3EKarya 6%3C/text%3E%3C/svg%3E'"><div class="gallery-label">Karya 6</div></div>
      </div>
    </div>
  </section>

  <!-- GALERI (masonry) -->
  <section id="galeri">
    <div class="container">
      <h2 class="section-title fade-in">Galeri Foto</h2>
      <div class="masonry-grid" id="galeriGrid">
        <!-- Ganti dengan foto pribadi -->
        <div class="gallery-item fade-in"><img src="" alt="Foto galeri 1" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 300 300%22%3E%3Crect width=%22300%22 height=%22300%22 fill=%22%23d9e2ec%22/%3E%3Ctext x=%2260%22 y=%22160%22 font-family=%22Poppins%22 font-size=%2224%22 fill=%22%235a6c7e%22%3EGaleri 1%3C/text%3E%3C/svg%3E'"><div class="gallery-label">Galeri 1</div></div>
        <div class="gallery-item fade-in"><img src="" alt="Foto galeri 2" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 300 300%22%3E%3Crect width=%22300%22 height=%22300%22 fill=%22%23d9e2ec%22/%3E%3Ctext x=%2260%22 y=%22160%22 font-family=%22Poppins%22 font-size=%2224%22 fill=%22%235a6c7e%22%3EGaleri 2%3C/text%3E%3C/svg%3E'"><div class="gallery-label">Galeri 2</div></div>
        <div class="gallery-item fade-in"><img src="" alt="Foto galeri 3" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 300 300%22%3E%3Crect width=%22300%22 height=%22300%22 fill=%22%23d9e2ec%22/%3E%3Ctext x=%2260%22 y=%22160%22 font-family=%22Poppins%22 font-size=%2224

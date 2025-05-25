<template>
  <div class="about">
    <h1>Tentang Toko Es Krim Kami</h1>
    <p class="intro">
      Kami adalah toko es krim lokal yang berdedikasi untuk menyajikan kebahagiaan dalam setiap rasa. Berdiri sejak 2024, kami telah menjadi pilihan keluarga untuk menikmati es krim segar dan kreatif.
    </p>

    <div class="section">
      <h2>Rasa Otentik & Segar</h2>
      <p>
        Semua es krim kami dibuat dari bahan-bahan alami tanpa pengawet dan varian yang unik.
      </p>
    </div>

    <div class="section">
      <h2>Dibuat Dengan Sepenuh Hati</h2>
      <p>
        Dibuat secara handmade oleh tim kami yang kreatif dan berdedikasi. Kami percaya bahwa es krim adalah karya seni yang bisa membawa senyum untuk siapa saja.
      </p>
    </div>

    <div class="section">
      <h2>Lokasi Kami</h2>
      <p>
        Toko kami hadir di pusat kota dengan suasana ceria dan ramah anak. Kami juga melayani pesan antar dan pemesanan acara khusus!
      </p>
    </div>

    <div class="contact-section">
      <h2>Kontak Kami</h2>
      <p><strong>Alamat:</strong> Jl. Bahagia No. 15, Bandung</p>
      <p>
        <strong>WhatsApp:</strong>
        <a href="https://wa.me/6281234567890" target="_blank" class="link">0812-3456-7890</a>
      </p>
      <p>
        <strong>Instagram:</strong>
        <a href="https://instagram.com/eskimtia" target="_blank" class="link">@eskimtia</a>
      </p>
      <p><strong>Email:</strong> eskimtia@gmail.com</p>
    </div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Fredoka:wght@400;600&display=swap');

.about {
  max-width: 820px;
  margin: 40px auto;
  padding: 40px 30px;
  background: linear-gradient(135deg, #fff0f5, #ffeef2, #fffaf0);
  border-radius: 24px;
  box-shadow: 0 8px 20px rgba(255, 183, 197, 0.3);
  font-family: 'Fredoka', cursive;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 25px;
  color: #f77ca4;
  text-align: center;
  text-shadow: 1px 1px #ffe1ed;
}

.intro {
  font-size: 1.15rem;
  text-align: center;
  margin-bottom: 40px;
  color: #5f4a4a;
}

.section {
  background: #fffafc;
  border: 2px dashed #ffcce0;
  border-radius: 20px;
  padding: 20px 25px;
  margin-bottom: 25px;
  transition: transform 0.3s ease;
}

.section:hover {
  transform: scale(1.02);
  box-shadow: 0 6px 15px rgba(255, 180, 210, 0.3);
}

.section h2,
.contact-section h2 {
  font-size: 1.4rem;
  color: #f08a5d;
  margin-bottom: 10px;
}

.section p,
.contact-section p {
  font-size: 1rem;
  color: #5d5d5d;
  line-height: 1.6;
}

.contact-section {
  background: #fff8fb;
  border: 2px dashed #ffbdd3;
  border-radius: 20px;
  padding: 20px 25px;
  margin-top: 30px;
}

a.link {
  color: #f95b99;
  text-decoration: none;
  font-weight: 600;
}

a.link:hover {
  text-decoration: underline;
}
</style>

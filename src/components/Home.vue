<template>
  <div class="home">
    <div class="hero">
      <h1>Selamat Datang di Toko Es Krim Tia</h1>
      <p>Segarkan harimu dengan rasa manis dan tampilan ceria</p>
    </div>

    <div class="features">
      <div class="feature-card">
        <h2>Bahan Segar</h2>
        <p>Buah asli dan susu premium tanpa pengawet.</p>
      </div>
      <div class="feature-card">
        <h2>Rasa Unik</h2>
        <p>Varian rasa kreatif seperti bubblegum dan matcha cookies.</p>
      </div>
      <div class="feature-card">
        <h2>Tempat Ceria</h2>
        <p>Toko colorful yang nyaman untuk anak-anak dan keluarga.</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Fredoka:wght@400;600&display=swap');

.home {
  padding: 50px 20px;
  background: linear-gradient(135deg, #ffe3f5, #ffeafc, #fff7f7);
  text-align: center;
  font-family: 'Fredoka', cursive;
  animation: softFade 2s ease-in-out;
}

@keyframes softFade {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.hero h1 {
  font-size: 2.8rem;
  color: #f870a2;
  margin-bottom: 15px;
  text-shadow: 2px 2px #ffd6e8;
}

.hero p {
  font-size: 1.2rem;
  color: #5f4b4b;
  margin-bottom: 40px;
}

.features {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 30px;
}

.feature-card {
  background: linear-gradient(180deg, #fff0f5, #fffdfd);
  border-radius: 25px;
  width: 260px;
  padding: 30px 25px;
  border: 3px dashed #ffc7e2;
  box-shadow: 0 10px 20px rgba(255, 170, 200, 0.3);
  transition: all 0.4s ease;
  animation: floatCard 3s ease-in-out infinite;
}

.feature-card:hover {
  transform: scale(1.05);
  background: linear-gradient(180deg, #ffe9f2, #ffffff);
  box-shadow: 0 12px 28px rgba(255, 140, 190, 0.5);
}

.feature-card h2 {
  font-size: 1.4rem;
  color: #f95b99;
  margin-bottom: 12px;
  font-weight: 600;
  text-shadow: 1px 1px #ffecf2;
}

.feature-card p {
  font-size: 1rem;
  color: #6f6f6f;
  line-height: 1.6;
}

@keyframes floatCard {
  0% { transform: translateY(0px); }
  50% { transform: translateY(-5px); }
  100% { transform: translateY(0px); }
}
</style>
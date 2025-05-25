<template>
  <nav class="navbar">
    <router-link to="/" class="link">Beranda</router-link>
    <router-link to="/about" class="link">Tentang</router-link>
    <router-link to="/product" class="link">Produk</router-link>
    <router-link to="/pemesanan" class="link">Pemesanan</router-link>
  </nav>
</template>

<style scoped>
.navbar {
  padding: 20px;
  background-color: #f8f0f5;
  display: flex;
  justify-content: center;
  gap: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.link {
  text-decoration: none;
  color: #a94c8d;
  font-weight: bold;
  transition: color 0.3s ease;
}

.link:hover {
  color: #d66ba0;
}
</style>

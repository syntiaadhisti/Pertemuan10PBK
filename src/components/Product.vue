<template>
  <div class="product-page">
    <h1>🍦 Pilihan Es Krim Imut</h1>
    <div class="product-list">
      <div v-for="item in products" :key="item.id" class="product-card">
        <img :src="item.image" :alt="item.name" />
        <h2>{{ item.name }}</h2>
        <p class="description">{{ item.description }}</p>
        <p class="price">Rp {{ item.price.toLocaleString('id-ID') }}</p>
        <button @click="pesan(item)">Pesan Sekarang 💌</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        {
          id: 1,
          name: 'Strawberry ice creem',
          description: 'Rasa stroberi dengan fla strawberry yang melimpah dan menyegarkan.',
          price: 18000,
          image: new URL('../assets/Homemade Strawberry Ice Cream.jpg', import.meta.url).href
        },
        {
          id: 2,
          name: 'Vanilla Cloud',
          description: 'Lembut seperti awan dengan sprinkle yang menambahkan sentuhan manis.',
          price: 16000,
          image: new URL('../assets/vanila sprinkle.jpg', import.meta.url).href
        },
        {
          id: 3,
          name: 'Minty Bear',
          description: 'Es krim mint segar dengan cokelat choco-chip lucu.',
          price: 19000,
          image: new URL('../assets/choco mint.jpg', import.meta.url).href
        },
        {
          id: 4,
          name: 'Lotus Ice Cream',
          description: 'Ice cream dengan rasa Biskuit Lotus yang khas.',
          price: 20000,
          image: new URL('../assets/Homemade Biscoff Ice Cream (1).jpg', import.meta.url).href
        }
      ]
    };
  },
  methods: {
    pesan(item) {
      this.$router.push({
        path: '/pemesanan',
        query: {
          produk: item.name,
          harga: item.price
        }
      });
    }
  }
}

</script>

<style scoped>
.product-page {
  padding: 40px 20px;
  background-color: #fff0f5;
  text-align: center;
  font-family: 'Comic Sans MS', 'Poppins', cursive;
}

h1 {
  font-size: 2.2rem;
  margin-bottom: 30px;
  color: #ff6fa1;
  text-shadow: 1px 1px #ffe4ec;
}

.product-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 25px;
}

.product-card {
  background: #ffffff;
  border-radius: 18px;
  padding: 20px;
  box-shadow: 0 8px 16px rgba(255, 182, 193, 0.25);
  transition: transform 0.2s;
  border: 2px dashed #ffd9ec;
}

.product-card:hover {
  transform: scale(1.05);
}

img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  border-radius: 14px;
  margin-bottom: 15px;
  border: 3px solid #ffe4f0;
}

h2 {
  font-size: 1.2rem;
  color: #ff80ab;
  margin-bottom: 10px;
}

.description {
  font-size: 0.95rem;
  color: #776f6f;
  margin-bottom: 10px;
}

.price {
  font-size: 1.1rem;
  font-weight: bold;
  color: #ff4d88;
  background-color: #fff0f5;
  padding: 6px 12px;
  border-radius: 12px;
  display: inline-block;
}

button {
  margin-top: 10px;
  background-color: #ff80ab;
  color: white;
  border: none;
  padding: 8px 14px;
  border-radius: 12px;
  cursor: pointer;
  transition: background-color 0.2s;
  font-weight: bold;
}

button:hover {
  background-color: #ff4d88;
}
</style>

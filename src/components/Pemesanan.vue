<template>
  <div class="pemesanan-page">
    <h1>Pesan Es Krim 🍦</h1>
    <p class="subtext">Isi form di bawah untuk melakukan pemesanan es krim favoritmu!</p>

    <div class="pemesanan-container">
      <!-- Form pemesanan -->
      <form class="pemesanan-form" @submit.prevent="kirimPesanan" v-if="!pesananTerkirim">
        <p v-if="produk && harga">
          <strong>Produk yang dipilih:</strong> {{ produk }} <br />
          <strong>Harga:</strong> Rp {{ harga.toLocaleString() }}
        </p>

        <input type="text" v-model="nama" placeholder="Nama Kamu" required />
        <input type="tel" v-model="telepon" placeholder="Nomor Telepon Aktif" required />
        <input type="number" v-model.number="jumlah" min="1" placeholder="Jumlah Pesanan" required />
        <textarea v-model="alamat" rows="3" placeholder="Alamat Rumah" required></textarea>
        <textarea v-model="pesan" rows="3" placeholder="Catatan Tambahan (opsional)"></textarea>

        <!-- Metode Pembayaran -->
        <div class="metode-pembayaran">
          <p><strong>Metode Pembayaran:</strong></p>
          <label>
            <input type="radio" value="Transfer Bank" v-model="metodePembayaran" required />
            Transfer Bank
          </label>
          <label>
            <input type="radio" value="Cash on Delivery (COD)" v-model="metodePembayaran" />
            Cash on Delivery (COD)
          </label>
          <label>
            <input type="radio" value="E-Wallet (Gopay/Dana/OVO)" v-model="metodePembayaran" />
            E-Wallet (Gopay/Dana/OVO)
          </label>
        </div>

        <button type="submit">Kirim Pesanan 💌</button>
      </form>

      <!-- Konfirmasi setelah kirim -->
      <div class="confirmation" v-else>
        <h2>🎉 Pesanan Diterima!</h2>
        <p>Terima kasih, pesanan kamu sedang kami proses 🍨</p>
        <div class="pesanan-detail">
          <p><strong>Nama:</strong> {{ nama }}</p>
          <p><strong>Telepon:</strong> {{ telepon }}</p>
          <p><strong>Jumlah:</strong> {{ jumlah }} es krim</p>
          <p><strong>Alamat:</strong> {{ alamat }}</p>
          <p><strong>Catatan:</strong> {{ pesan || 'Tidak ada' }}</p>
          <p v-if="produk && harga">
            <strong>Produk:</strong> {{ produk }} <br />
            <strong>Harga:</strong> Rp {{ harga.toLocaleString() }}
          </p>
          <p><strong>Metode Pembayaran:</strong> {{ metodePembayaran }}</p>
        </div>
      </div>
    </div>

    <!-- Pop-up notifikasi -->
    <div v-if="showPopup" class="popup">
      <div class="popup-content">
        <p>🍧 Pesanan kamu telah berhasil dikirim!</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'

const nama = ref('')
const telepon = ref('')
const jumlah = ref(1)
const alamat = ref('')
const pesan = ref('')
const metodePembayaran = ref('')

const produk = ref('')
const harga = ref(0)

const pesananTerkirim = ref(false)
const showPopup = ref(false)

const route = useRoute()

onMounted(() => {
  if (route.query.produk) {
    produk.value = route.query.produk
  }
  if (route.query.harga) {
    harga.value = Number(route.query.harga)
  }
})

function kirimPesanan() {
  if (jumlah.value < 1) {
    alert('Jumlah pesanan harus minimal 1!')
    return
  }
  if (!metodePembayaran.value) {
    alert('Mohon pilih metode pembayaran terlebih dahulu!')
    return
  }

  pesananTerkirim.value = true
  showPopup.value = true

  setTimeout(() => {
    showPopup.value = false
  }, 3000)

  setTimeout(() => {
    resetForm()
    pesananTerkirim.value = false
    produk.value = ''
    harga.value = 0
    metodePembayaran.value = ''
  }, 10000)
}

function resetForm() {
  nama.value = ''
  telepon.value = ''
  jumlah.value = 1
  alamat.value = ''
  pesan.value = ''
}
</script>

<style scoped>
.pemesanan-page {
  padding: 40px 20px;
  background-color: #fff0f7;
  font-family: 'Comic Sans MS', 'Poppins', cursive;
  text-align: center;
}

h1 {
  font-size: 2.3rem;
  color: #ff6fa1;
  margin-bottom: 10px;
}

.subtext {
  font-size: 1.05rem;
  color: #666;
  margin-bottom: 30px;
}

.pemesanan-container {
  display: flex;
  justify-content: center;
}

.pemesanan-form,
.confirmation {
  background: #ffffff;
  padding: 25px;
  border-radius: 16px;
  width: 320px;
  box-shadow: 0 6px 12px rgba(255, 182, 193, 0.2);
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.pemesanan-form input,
.pemesanan-form textarea {
  padding: 10px 14px;
  border-radius: 10px;
  border: 1px solid #ffb6c1;
  font-size: 0.95rem;
  background-color: #fff8fb;
}

.pemesanan-form button {
  background-color: #ff80ab;
  color: white;
  border: none;
  padding: 10px;
  font-weight: bold;
  border-radius: 12px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.pemesanan-form button:hover {
  background-color: #ff4d88;
}

.confirmation h2 {
  color: #ff6fa1;
  margin-bottom: 10px;
}

.confirmation p {
  font-size: 1rem;
  color: #555;
}

.pesanan-detail {
  background-color: #fff8fb;
  padding: 10px;
  border-radius: 10px;
  text-align: left;
  margin-top: 15px;
  font-size: 0.95rem;
}

/* Metode Pembayaran */
.metode-pembayaran {
  text-align: left;
  margin: 10px 0 15px;
  font-size: 0.95rem;
  color: #555;
}

.metode-pembayaran label {
  display: block;
  margin-bottom: 6px;
  cursor: pointer;
}

.metode-pembayaran input[type="radio"] {
  margin-right: 8px;
}

/* Pop-up tengah layar */
.popup {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #ffebf1;
  border: 1px solid #ff6fa1;
  padding: 15px 25px;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(255, 105, 135, 0.3);
  z-index: 999;
  font-weight: bold;
  color: #d63384;
  animation: fadeInOut 3s ease-in-out;
  text-align: center;
  min-width: 250px;
}

@keyframes fadeInOut {
  0% { opacity: 0; transform: translate(-50%, calc(-50% - 20px)); }
  10% { opacity: 1; transform: translate(-50%, -50%); }
  90% { opacity: 1; }
  100% { opacity: 0; transform: translate(-50%, calc(-50% - 20px)); }
}
</style>

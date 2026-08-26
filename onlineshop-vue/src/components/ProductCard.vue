<script setup>
import { ref } from "vue";

defineProps({
  nama: { type: String, required: true },
  harga: { type: Number, required: true },
  gambar: { type: String, required: true },
});

const gambarDipilih = ref(null);

function bukaPreview(src) {
  gambarDipilih.value = src;
}

function tutupPreview() {
  gambarDipilih.value = null;
}

function tambahKeKeranjang(nama) {
  const suara = new Audio("/audio/notifikasi.mp3");
  suara.play();
  alert(`${nama} ditambahkan ke keranjang!`);
}
</script>

<template>
  <div class="card">
    <img :src="gambar" :alt="nama" @click="bukaPreview(gambar)" />
    <h3 class="card-nama">{{ nama }}</h3>
    <p class="card-harga">Rp {{ harga.toLocaleString("id-ID") }}</p>
    <button class="card-btn" @click="tambahKeKeranjang(nama)">
      Tambah ke Keranjang
    </button>
  </div>

  <div v-if="gambarDipilih" class="preview-overlay" @click="tutupPreview">
    <img :src="gambarDipilih" class="preview-besar" />
  </div>
</template>

<style scoped>
.card {
  border: 1px solid #ddd;
  border-radius: 10px;
  padding: 14px;
  width: 220px;
  text-align: center;
  background-color: #fff;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.14);
}

.card img {
  width: 100%;
  border-radius: 6px;
  cursor: pointer;
}

.card-nama {
  margin: 10px 0 4px;
  font-size: 1rem;
}

.card-harga {
  color: #198754;
  font-weight: 600;
}

.card-btn {
  margin-top: 8px;
  padding: 8px 16px;
  border: none;
  border-radius: 6px;
  background: #0475f7;
  color: white;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.2s ease;
}

.card-btn:hover {
  background: #0356c2;
}

.preview-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: zoom-out;
  z-index: 1000;
}

.preview-besar {
  max-width: 80%;
  max-height: 80%;
  border-radius: 8px;
}
</style>

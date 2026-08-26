<script setup>
// Kartu produk: menerima data produk dari halaman yang memakainya
defineProps({
  nama: { type: String, required: true },
  harga: { type: Number, required: true },
  gambar: { type: String, required: true },
});
</script>

<template>
  <div class="card">
    <img :src="gambar" :alt="nama" class="card-gambar" />
    <h3 class="card-nama">{{ nama }}</h3>
    <p class="card-harga">Rp {{ harga.toLocaleString("id-ID") }}</p>
  </div>
</template>

<style scoped>
.card {
  width: 200px;
  box-sizing: border-box;
  border: 1px solid #dee2e6;
  border-radius: 16px;
  padding: 20px;
  text-align: center;
  background-color: #fff;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  transition:
    transform 0.2s ease,
    box-shadow 0.2s ease;
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.14);
}

.card-gambar {
  width: 100%;
  border-radius: 6px;
}

.card-nama {
  margin: 10px 0 4px;
  font-size: 1rem;
}

.card-harga {
  color: #198754;
  font-weight: 600;
}
</style>

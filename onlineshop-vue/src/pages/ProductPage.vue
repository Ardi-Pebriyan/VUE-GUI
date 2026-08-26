<script setup>
import ProductCard from "../components/ProductCard.vue";

// Daftar produk yang dijual
const daftarProduk = [
  { id: 1, nama: "Kaos Sekolah", harga: 75000, gambar: "/images/kaos.svg" },
  { id: 2, nama: "Topi Sekolah", harga: 35000, gambar: "/images/topi.svg" },
  { id: 3, nama: "Tas Sekolah", harga: 120000, gambar: "/images/tas.svg" },
];
</script>

<template>
  <main>
    <!-- Banner: judul halaman, warnanya senada dengan landing page dan halaman lainnya -->
    <section class="banner">
      <h1>Produk Kami</h1>
    </section>

    <!-- Daftar produk yang dijual -->
    <section class="produk">
      <div class="grid">
        <ProductCard
          v-for="produk in daftarProduk"
          :key="produk.id"
          :nama="produk.nama"
          :harga="produk.harga"
          :gambar="produk.gambar"
        />
      </div>
    </section>
  </main>
</template>

<style scoped>
/* ===== Banner halaman ===== */
.banner {
  padding: 48px 24px;
  text-align: center;
  color: #fff;
  background: linear-gradient(135deg, #2e2e3b, #0408f3);
}

.banner h1 {
  margin: 0;
  font-size: 2.5rem;
}

/* ===== Daftar produk ===== */
.produk {
  max-width: 900px;
  margin: 0 auto;
  padding: 48px 24px;
}

.grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 24px;
}
</style>

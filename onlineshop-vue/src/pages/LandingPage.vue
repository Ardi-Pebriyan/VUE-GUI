<script setup>
import { RouterLink } from "vue-router";

const daftarFitur = [
  {
    ikon: "🛒",
    judul: "Belanja Mudah",
    deskripsi: "Cari dan pesan produk dalam beberapa klik saja.",
  },
  { ikon: "🚚", judul: "Pengiriman Cepat", deskripsi: "Barang dikirim ke alamatmu tanpa ribet." },
  {
    ikon: "💳",
    judul: "Pembayaran Aman",
    deskripsi: "Transaksi aman dengan berbagai metode bayar.",
  },
]; 
</script>

<template>
  <main>
    <!-- Bagian hero: judul, penjelasan singkat, dan tombol ke halaman produk -->
    <section class="hero">
      <h1 class="hero-judul">Selamat Datang di Ardishop</h1>
      <p class="hero-deskripsi">
        Belanja gampang, sekolah senang — perlengkapan sekolah lengkap dalam satu tempat.
      </p>
      <RouterLink to="/product" class="cta">Lihat Produk</RouterLink>
    </section>

    <!-- Bagian fitur: tiga kartu keunggulan toko -->
    <section class="features">
      <h2 class="features-judul">Kenapa Belanja di Sini?</h2>
      <div class="feature-grid">
        <article v-for="fitur in daftarFitur" :key="fitur.judul" class="feature-card">
          <span class="feature-ikon">{{ fitur.ikon }}</span>
          <h3 class="feature-judul">{{ fitur.judul }}</h3>
          <p class="feature-deskripsi">{{ fitur.deskripsi }}</p>
        </article>
      </div>
    </section>
  </main>
</template>

<style scoped>
/* ===== Bagian hero ===== */
.hero {
  padding: 64px 24px;
  text-align: center;
  color: #0c47e9;
}

.hero-judul {
  margin: 0 0 12px;
  font-size: 2.75rem;
}

.hero-deskripsi {
  max-width: 480px;
  margin: 0 auto 28px;
  font-size: 1.1rem;
  line-height: 1.6;
  opacity: 0.92;
}

.cta {
  display: inline-block;
  padding: 12px 32px;
  background-color: #2e2e3b;
  color: #0404f3;
  font-size: 1rem;
  font-weight: 600;
  text-decoration: none;
  border-radius: 999px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  transition:
    transform 0.2s ease,
    box-shadow 0.2s ease;
}

.cta:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
}

/* ===== Bagian fitur ===== */
.features {
  padding: 48px 24px;
}

.features-judul {
  margin: 0 0 28px;
  text-align: center;
}

.feature-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 24px;
}

.feature-card {
  flex: 1 1 240px;
  max-width: 320px;
  padding: 24px;
  text-align: center;
  background-color: #fff;
  border: 1px solid #dee2e6;
  border-radius: 16px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  transition:
    transform 0.2s ease,
    box-shadow 0.2s ease;
}

.feature-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.14);
}

.feature-ikon {
  font-size: 2.5rem;
  display: block;
  margin-bottom: 12px;
}

.feature-judul {
  margin: 0 0 8px;
  font-size: 1.15rem;
}

.feature-deskripsi {
  margin: 0;
  color: #6c757d;
  line-height: 1.6;
}
</style>

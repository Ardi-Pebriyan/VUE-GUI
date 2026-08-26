<script setup>
import TeamCard from "../components/TeamCard.vue";

// Daftar anggota tim yang ditampilkan pada halaman tentang
const daftarTim = [
  { nama: "Raka Pratama", jabatan: "Pemilik Toko" },
  { nama: "Tia Anggraini", jabatan: "Desainer Produk" },
  { nama: "Dimas Saputra", jabatan: "Admin Penjualan" },
];
</script>

<template>
  <main>
    <!-- Banner: judul halaman, warnanya senada dengan landing page -->
    <section class="banner">
      <h1>Tentang Kami</h1>
    </section>

    <!-- Bagian cerita kami: teks di kiri dan gambar di kanan -->
    <section class="cerita">
      <div class="cerita-teks">
        <h2>Cerita Kami</h2>
        <p>
          Ardishop lahir dari kelas PPLG yang ingin membuktikan kalau ilmu coding bisa jadi karya
          nyata dan juga awalnya saya coba-coba tpi malah ketagihan.
        </p>
        <p>
          Semua produk yang ada disini dipilih oleh KING ARDI, oleh karena itu harganya jadi ramah kantong untuk para pelajar, dan juga pelayanannya sangat ramah.  ayo sekarang saatnya giliranmu belanja di sini!
        </p>
      </div>
      <div class="cerita-gambar">
        <span>🏫</span>
      </div>
    </section>

    <!-- Bagian tim kami: kartu anggota dari daftarTim -->
    <section class="tim">
      <h2>Tim Kami</h2>
      <div class="tim-grid">
        <TeamCard
          v-for="anggota in daftarTim"
          :key="anggota.nama"
          :nama="anggota.nama"
          :jabatan="anggota.jabatan"
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

/* ===== Cerita kami: dua kolom merata ===== */
.cerita {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 32px;
  max-width: 900px;
  margin: 0 auto;
  padding: 48px 24px;
}

.cerita-teks {
  flex: 1;
  min-width: 260px;
}

.cerita-teks h2 {
  margin: 0 0 16px;
}

.cerita-teks p {
  margin: 0 0 12px;
  color: #495057;
  line-height: 1.7;
}

.cerita-gambar {
  flex: 1;
  min-width: 260px;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 240px;
  font-size: 5rem;
  background: linear-gradient(135deg, #ede9fe, #f5d0fe);
  border-radius: 16px;
}

/* ===== Tim kami ===== */
.tim {
  padding: 0 24px 48px;
}

.tim h2 {
  margin: 0 0 24px;
  text-align: center;
}

.tim-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 24px;
}
</style>

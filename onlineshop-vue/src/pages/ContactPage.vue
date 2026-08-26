<script setup>
// Daftar informasi kontak yang ditampilkan di sebelah kiri
const infoKontak = [
  { ikon: "📍", judul: "Alamat", nilai: "Jl. Raya Soreang No. 123, Kab. Bandung" },
  { ikon: "☎️", judul: "Telepon", nilai: "(022) 589-1234" },
  { ikon: "✉️", judul: "Email", nilai: "info@ardishop.sch.id" },
  { ikon: "🕐", judul: "Jam Layanan", nilai: "Senin - Jumat, 08.00 - 16.00" },
];
</script>

<template>
  <main>
    <!-- Banner: judul halaman, warnanya senada dengan landing page dan about page -->
    <section class="banner">
      <h1>Hubungi Kami</h1>
    </section>

    <!-- Bagian kontak: info di kiri dan formulir di kanan -->
    <section class="kontak-grid">
      <div class="info">
        <h2>Info Kontak</h2>
        <div v-for="item in infoKontak" :key="item.judul" class="info-item">
          <span class="info-ikon">{{ item.ikon }}</span>
          <div>
            <h3>{{ item.judul }}</h3>
            <p>{{ item.nilai }}</p>
          </div>
        </div>
      </div>

      <form class="form">
        <h2>Kirim Pesan</h2>
        <label for="nama">Nama</label>
        <input id="nama" type="text" placeholder="Nama lengkap kamu" />

        <label for="email">Email</label>
        <input id="email" type="email" placeholder="email@kamu.com" />

        <label for="pesan">Pesan</label>
        <textarea id="pesan" rows="5" placeholder="Tulis pesan kamu di sini..."></textarea>

        <button type="submit">Kirim</button>
      </form>
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

/* ===== Dua kolom: info kontak dan formulir ===== */
.kontak-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 32px;
  max-width: 900px;
  margin: 0 auto;
  padding: 48px 24px;
}

.info,
.form {
  flex: 1;
  min-width: 280px;
  padding: 24px;
  background-color: #fff;
  border: 1px solid #dee2e6;
  border-radius: 16px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}

.info h2,
.form h2 {
  margin: 0 0 20px;
  color: #2e2e3b;
}

/* ===== Baris info kontak ===== */
.info-item {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  margin-bottom: 16px;
}

.info-ikon {
  font-size: 1.5rem;
}

.info-item h3 {
  margin: 0 0 4px;
  font-size: 1rem;
}

.info-item p {
  margin: 0;
  color: #6c757d;
  line-height: 1.6;
}

/* ===== Field formulir ===== */
.form label {
  display: block;
  margin: 0 0 6px;
  font-weight: 600;
}

.form input,
.form textarea {
  width: 100%;
  box-sizing: border-box;
  padding: 10px 14px;
  margin-bottom: 16px;
  border: 1px solid #dee2e6;
  border-radius: 8px;
  font-family: inherit;
  font-size: 1rem;
}

.form input:focus,
.form textarea:focus {
  outline: none;
  border-color: #0475f7;
  box-shadow: 0 0 0 3px rgba(4, 117, 247, 0.15);
}

.form textarea {
  resize: vertical;
}

/* ===== Tombol kirim bergaya pil ===== */
.form button {
  width: 100%;
  padding: 12px 32px;
  background-color: #0475f7;
  color: #fff;
  font-size: 1rem;
  font-weight: 600;
  border: none;
  border-radius: 999px;
  cursor: pointer;
  transition:
    transform 0.2s ease,
    box-shadow 0.2s ease;
}

.form button:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(4, 117, 247, 0.4);
}
</style>

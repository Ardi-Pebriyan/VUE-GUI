<script setup>
// Kartu anggota tim: menerima data anggota dari halaman yang memakainya
defineProps({
  nama: { type: String, required: true },
  jabatan: { type: String, required: true },
});
</script>

<template>
  <div class="card">
    <div class="avatar">{{ nama.charAt(0) }}</div>
    <h3 class="card-nama">{{ nama }}</h3>
    <p class="card-jabatan">{{ jabatan }}</p>
  </div>
</template>

<style scoped>
.card {
  width: 220px;
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

.avatar {
  width: 72px;
  height: 72px;
  margin: 0 auto 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.8rem;
  font-weight: 600;
  color: #fff;
  background: linear-gradient(135deg, #6366f1, #a855f7);
  border-radius: 50%;
}

.card-nama {
  margin: 0 0 6px;
  font-size: 1.05rem;
}

.card-jabatan {
  margin: 0;
  color: #6c757d;
}
</style>

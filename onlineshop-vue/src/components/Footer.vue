<script setup>
// Tahun otomatis mengikuti tahun sekarang
const tahun = new Date().getFullYear();
</script>

<template>
  <footer class="footer">
    <small>&copy; {{ tahun }} SMK Yadika Soreang &mdash; Onlineshop Sekolah</small>
  </footer>
</template>

<style scoped>
.footer {
  text-align: center;
  padding: 16px;
  color: #6c757d;
  background-color: #f1f3f5;
  border-top: 1px solid #dee2e6;
}
</style>

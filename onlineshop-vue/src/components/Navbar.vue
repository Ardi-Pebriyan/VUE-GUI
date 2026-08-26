<script setup>
// Nama toko, ditampilkan di kiri navbar
const namaToko = "SMK Yadika Soreang - Onlineshop";

// Daftar menu (label + rute tujuan)
const menu = [
  { label: "Beranda", rute: "/" },
  { label: "Produk", rute: "/product" },
  { label: "Tentang", rute: "/about" },
  { label: "Contact", rute: "/contact" },
];
</script>

<template>
  <header class="navbar">
    <RouterLink to="/" class="navbar-brand">{{ namaToko }}</RouterLink>

    <nav class="navbar-menu">
      <RouterLink v-for="item in menu" :key="item.rute" :to="item.rute" class="navbar-link">
        {{ item.label }}
      </RouterLink>
    </nav>
  </header>
</template>

<style scoped>
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  padding: 14px 24px;
  background-color: #0475f7;
  color: #fff;
}

.navbar-brand {
  font-weight: 700;
  font-size: 1.1rem;
  color: #fff;
  text-decoration: none;
}

.navbar-menu {
  display: flex;
  gap: 16px;
}

.navbar-link {
  color: #e3ecff;
  text-decoration: none;
  padding: 4px 10px;
  border-radius: 6px;
}

.navbar-link:hover {
  background-color: rgba(255, 255, 255, 0.15);
}

/* Tautan yang sedang aktif (rute aktif) */
.navbar-link.router-link-active {
  background-color: #0a58ca;
  color: #fff;
}
</style>

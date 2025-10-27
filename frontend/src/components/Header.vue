<template>
  <header class="navbar">
    <div class="container">
      <!-- Logo -->
      <div class="logo">
        <img src="D:\noteboard-ai\frontend\src\assets\Logo-NoteBoard.png" alt="NoteBoard AI" />
        <span class="brand-name">NoteBoard <span class="highlight">AI</span></span>
      </div>

      <!-- Navigation Links -->
      <nav class="nav-links">
        <a 
          v-for="link in navLinks" 
          :key="link.name" 
          :href="link.href" 
          class="nav-item"
          :class="{ active: activeLink === link.name }"
          @click.prevent="setActive(link.name)"
        >
          {{ link.name }}
        </a>
        <a href="#mulai" class="nav-item btn-primary">Mulai Coba</a>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue"

const activeLink = ref("Beranda")

const navLinks = [
  { name: "Beranda", href: "#beranda" },
  { name: "Fitur", href: "#fitur" },
  { name: "Mulai Coba", href: "#Mulai" },
]

const setActive = (name) => {
  activeLink.value = name
}
</script>

<style scoped>
/* Container umum */
.navbar {
  background: #ffffff;
  box-shadow: 0 2px 8px rgba(0,0,0,0.05);
  padding: 16px 32px;
  position: sticky;
  top: 0;
  z-index: 50;
}

.container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1200px;
  margin: auto;
}

/* Logo */
.logo {
  display: flex;
  align-items: center;
  gap: 8px;
}

.logo img {
  width: 40px;
  height: 40px;
}

.brand-name {
  font-size: 20px;
  font-weight: 600;
  color: #1f2937;
}

.highlight {
  color: #3B82F6;
}

/* Nav links */
.nav-links {
  display: flex;
  align-items: center;
  gap: 24px;
}

.nav-item {
  text-decoration: none;
  color: #4B5563;
  font-weight: 500;
  transition: color 0.2s;
}

.nav-item:hover {
  color: #2563EB;
}

.nav-item.active {
  color: #3B82F6;
  border-bottom: 2px solid #3B82F6;
  padding-bottom: 4px;
}

/* Tombol utama */
.btn-primary {
  background: #3B82F6;
  color: white !important;
  padding: 8px 16px;
  border-radius: 6px;
  font-weight: 500;
}

.btn-primary:hover {
  background: #2563EB;
}
</style>

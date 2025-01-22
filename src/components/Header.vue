<template>
  <header>
    <nav class="header-container">
      <!-- Logo avec lien vers l'accueil -->
      <div class="logo">
        <a href="#" @click.prevent="scrollToTop">
          <img src="../assets/img/adel-portfolio.png" alt="Logo Adel CAMILLERI" />
        </a>
      </div>

      <!-- Titre -->
      <div class="titre">
        <h1>Portfolio de Adel CAMILLERI</h1>
      </div>

      <!-- Menu de navigation -->
      <div class="nav-links">
        <a href="#presentation" class="nav-link">Présentation</a>
        <a href="#creations" class="nav-link">Créations</a>
        <a href="#contact" class="nav-link">Contact</a>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'TheHeader',
  methods: {
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
    }
  }
}
</script>

<style>
header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
}

.header-container {
  height: 80px;
  width: 100%;
  background-color: #007198;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 2rem;
  box-sizing: border-box;
  max-width: 100%;
  overflow-x: hidden;
}

h1 {
color: #ffffff;
}

.logo {
  height: 60px;
}

.logo img {
  height: 100%;
  width: auto;
}

.titre {
  margin-left: 15rem;
}

.titre h1 {
  font-size: 1.5rem;
  margin: 0;
}

.nav-links {
  display: flex;
  gap: 1rem;
  margin-left: auto;
}

.nav-link {
  text-decoration: none;
  color: #ffffff;
  font-weight: 500;
  padding: 0.5rem 1rem;
  transition: all 0.3s ease;
}

.nav-link:hover {
  color: #007bff;
  text-decoration: underline;
}

@media (max-width: 768px) {
  .header-container {
    flex-direction: column;
    height: auto;
    padding: 1rem;
  }

  .nav-links {
    flex-direction: column;
    align-items: center;
    gap: 1rem;
    width: 100%;
    padding: 1rem 0;
  }
  
  .titre h1 {
    font-size: 1.2rem;
    text-align: center;
  }
}
</style>

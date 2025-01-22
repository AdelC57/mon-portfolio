# NotFound.vue
<template>
  <div class="not-found">
    <img src="../assets/img/404.png" alt="404 Error" class="error-image">
    <h1>404</h1>
    <p>La page que vous recherchez n'existe pas</p>
    <router-link to="/" class="home-link">Retour à l'accueil</router-link>
  </div>
</template>

<style scoped>
.not-found {
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  background-color: #f5f5f5;
}

.error-image {
  width: 300px;
  height: auto;
  margin-bottom: 2rem;
}

h1 {
  font-size: 6rem;
  color: #333;
  margin: 0;
}

p {
  font-size: 1.5rem;
  color: #666;
  margin: 1rem 0;
}

.home-link {
  margin-top: 2rem;
  padding: 1rem 2rem;
  background-color: #007bff;
  color: white;
  text-decoration: none;
  border-radius: 4px;
  transition: background-color 0.3s;
}

.home-link:hover {
  background-color: #0056b3;
}
</style>
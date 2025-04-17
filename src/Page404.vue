<template>
  <div class="not-found">
    <img src="../image/404.jpg" alt="Page non trouvée" />
    <h1>404</h1>
    <p>Oups ! Cette page n'existe pas.</p>
    <!-- Lien vers la page d'accueil -->
    <a class="back-home">Retour à l'accueil</a>
  </div>
</template>

<script>
export default {
  name: "Page404",
};
</script>

<style scoped>
.page-404 {
  text-align: center;
  padding: 50px;
}

img {
  max-width: 100%;
  height: auto;
}

h1 {
  font-size: 5rem;
  margin-top: 20px;
}

p {
  font-size: 1.2rem;
  margin-top: 10px;
}

.back-home {
  display: inline-block;
  padding: 10px 20px;
  margin-top: 20px;
  background-color: #007bff;
  color: white;
  text-decoration: none;
  border-radius: 5px;
}

.back-home:hover {
  background-color: #0056b3;
}
</style>

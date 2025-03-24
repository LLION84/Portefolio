<template>
  <header>
    <a href="">
      <img
        src="../image/MonLogo.png"
        alt="Logo du portfolio"
        class="profile-img"
      />
    </a>
    <nav class="lien-ancre">
      <ul>
        <li><a href="#présentation">Présentation</a></li>
        <li><a href="#projets">Projets</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>
</template>

<script setup></script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;500&display=swap");

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Poppins", sans-serif;
  font-weight: 700;
  color: #12110f;
}
body {
  background-color: #feecd4f2;
  font-family: "Roboto";
  font-weight: 400;
  color: #1c1816;
}
header {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  text-align: center;
  width: 100%;
  overflow: hidden; /* Empêche le débordement horizontal */
}

.profile-img {
  width: 100px;
  height: auto;
  border: 5px solid #4d3c2f;
  border-radius: 15px;
  padding: 2px;
  box-shadow: 0 4px 8px #322922;
  transition: all 0.3s ease;
}

.profile-img:hover {
  box-shadow: 0 6px 16px #28211d;
  transform: scale(1.05);
}

.lien-ancre {
  box-sizing: border-box;
  margin: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  margin: 25px auto;
  background-color: #28211d;
  overflow: hidden;
  max-width: 100%;
  width: 100vw;
  text-align: center;
}

.lien-ancre ul {
  list-style: none;
  display: flex;
  gap: 70px;
  padding: 0;
  justify-content: center;
  flex-wrap: wrap;
}

.lien-ancre a {
  text-decoration: none;
  color: #f2e1ca;
  background-color: #ad7f58;
  border-radius: 5px;
  border: 2px solid #ffbe8773;
  transition: all 0.3s ease;
  box-shadow: 0 4px 12px rgba(255, 255, 255, 0.1);
  display: inline-block; /* Assure que les liens prennent la taille définie */
  min-width: 120px; /* Assure une largeur minimum pour chaque bouton */
  height: 50px; /* Fixe la hauteur pour tous les boutons */
  text-align: center; /* Centre le texte */
  line-height: 50px; /* Centre le texte verticalement */
}

.lien-ancre a:hover {
  background-color: #4d3c2f;
  box-shadow: 0 6px 16px rgba(255, 255, 255, 0.2); /* Ombre plus prononcée au survol */
  transform: scale(1.05);
}

/* Media query pour les petits écrans */
@media (max-width: 768px) {
  .lien-ancre ul {
    flex-direction: column; /* Passe les liens à une disposition verticale */
    gap: 40px; /* Réduit l'espacement vertical entre les liens */
    margin-right: 0; /* Enlève la marge droite qui pourrait causer un débordement */
  }

  .lien-ancre a {
    font-size: 18px; /* Ajuste la taille de police */
  }

  .profile-img {
    width: 80px; /* Réduit la taille de l'image de profil sur petit écran */
    height: auto;
  }
}
</style>

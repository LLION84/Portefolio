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
  <main>
    <section class="Presentation">
      <h1>Présentation</h1>
      <p><strong>Blaise Zinou</strong></p>
    </section>
    <div class="flex-container">
      <section class="Parcours_objectif">
        <h2>Parcours/objectif</h2>
        <p>
          -Étudiant en développement web depuis un an au C.E.F, passionné
          d'informatique depuis l'adolescence.<br />
          -Devenir développeur full-stack en freelance pour apporter des
          solutions concrètes et innovantes.
        </p>
      </section>

      <section class="Skills">
        <h2>Mes Compétences</h2>
        <p>
          J'aime aider les gens à créer leur business en ligne et développer des
          sites ou applications utiles à la société. Je maîtrise :
        </p>
        <ul>
          <li>HTML, CSS, JavaScript</li>
          <li>Git, GitHub, VS Code</li>
          <li>Vue.js</li>
          <li>Next.js</li>
        </ul>
      </section>
    </div>
    <section class="Project_cv">
      <h1>Projet CV</h1>
    </section>
    <div class="project">
      <div class="modal-container">
        <div class="overlay modal"></div>
        <div class="modal">
          <button class="close-modal">x</button>
          <h1>Mon Projet CV</h1>
          <p>07/03/2024</p>
          <p>Fais avec : HTML et CSS</p>
          <a
            href="../CV/cvhtml.html"
            target="_blank"
            rel="noopener noreferrer"
            class="cv-button"
          >
            Consulter mon CV
          </a>
          <a
            href="https://github.com/LLION84/CV-num-rique"
            class="github-link"
            target="_blank"
          >
            <img
              src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png"
              alt="GitHub"
              class="github-icon"
            />
            GitHub Repository
          </a>
          <button class="close-modal">x</button>
        </div>
      </div>
      <button class="img-button">
        <img
          src="../image/imgexmpcv.png"
          alt="Miniature"
          class="img_miniature_cv"
        />
      </button>
    </div>
  </main>
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
  line-height: 1.3;
}
body {
  background-color: #feecd4f2;
  font-family: "Roboto";
  font-weight: 400;
  color: #1c1816;
  line-height: 1.6;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
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
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  padding: 25px;
  background-color: #dbb594;
}
.Presentation {
  text-align: center;
  width: 100%;
  background-color: #3e3128;
  color: #f2e1ca;
  border-radius: 6px;
}
.flex-container {
  display: flex;
  justify-content: space-around;
  align-items: stretch;
  gap: 20px;
  width: 100%;
}

.Parcours_objectif,
.Skills {
  flex: 1;
  background-color: #4d3c2f;
  color: #f2e1ca;
  padding: 10px;
  border-radius: 6px;
  min-width: 250px;
}

.Skills li {
  padding: 5px;
  transition: all 0.3s ease;
  cursor: default;
}

.Skills li:hover {
  transform: translateX(10px);
  color: #dbb594;
  font-weight: bold;
}

@media (max-width: 768px) {
  .flex-container {
    flex-direction: column;
  }
}
.Project_cv {
  text-align: center;
  width: 100%;
  background-color: #3e3128;
  color: #f2e1ca;
  border-radius: 6px;
}
.img_miniature_cv {
  width: 200px; /* Taille de base de l'image */
  padding: 5px;
  transition: transform 0.3s ease, box-shadow 0.3s ease; /* Transition fluide pour l'agrandissement et l'ombre */
  cursor: pointer;
  border-radius: 10px; /* Bordure arrondie pour l'image */
}

.img_miniature_cv:hover {
  transform: scale(1.1); /* Agrandissement de l'image au survol */
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2); /* Ombre portée pour donner de la profondeur */
}
.img-button {
  background: none; /* Pas de fond pour le bouton */
  border: none; /* Retirer la bordure par défaut du bouton */
  padding: 0; /* Enlever tout padding par défaut */
  cursor: pointer; /* Change le curseur pour indiquer que c'est cliquable */
}
.cv-button {
  padding: 12px 24px;
  background-color: #ad7f58;
  color: #ffffff;
  text-decoration: none;
  font-weight: 600;
  font-size: 16px;
  border-radius: 8px;
  border: 2px solid #ffbe87;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.cv-button:hover {
  background-color: #ad7f58;
  background-color: #4d3c2f;
  box-shadow: 0 6px 16px rgba(255, 255, 255, 0.2);
  transform: scale(1.05);
}
.github-link {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 6px 12px;
  background-color: #24292e;
  color: #ffffff;
  text-decoration: none;
  font-weight: bold;
  border-radius: 6px;
  box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.1);
  font-size: 14px;
  transition: background-color 0.3s, transform 0.3s;
}

.github-link:hover {
  background-color: #444c56;
  transform: translateY(-1px);
}

.github-icon {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  padding: 2px;
  background-color: #ffffff;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
}
</style>

<template>
  <div id="app">
    <header>
      <div id="top"></div>
      <a href="#top" class="logo-scroll">
        <img
          src="../image/MonLogo.png"
          alt="Logo du portfolio"
          class="profile-img"
        />
      </a>
      <nav class="lien-ancre">
        <ul>
          <li><a href="#présentation" class="link">Présentation</a></li>
          <li><a href="#projets" class="link">Projets</a></li>
          <li><a href="#contact" class="link">Contact</a></li>
          <li>
            <a class="link">Autre</a>
          </li>
        </ul>
      </nav>
    </header>
  </div>
  <main>
    <section class="Presentation" id="présentation" data-aos="fade-up">
      <h1>Présentation</h1>
      <p><strong>Blaise Zinou</strong></p>
    </section>
    <div class="flex-container" data-aos="fade-up">
      <section class="Parcours_objectif" data-aos="fade-up">
        <h2>Parcours/objectif</h2>
        <p>
          -Étudiant en développement web depuis un an au C.E.F, passionné
          d'informatique depuis l'adolescence.<br />
          -Devenir développeur full-stack en freelance pour apporter des
          solutions concrètes et innovantes.
        </p>
      </section>

      <section class="Skills" data-aos="fade-up">
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
    <section class="Project_modals" data-aos="fade-up" id="projets">
      <h1>Projet CV</h1>
    </section>
    <div class="project">
      <div class="modal-container">
        <div class="overlay_modal-trigger"></div>

        <div class="modal">
          <button class="close-modal_modal-trigger">X</button>
          <p>07/03/2024</p>
          <h1>Mon Projet CV</h1>
          <p>Fait avec : HTML et CSS</p>
          <a
            href="../CV/cvhtml.html"
            target="_blank"
            rel="noopener noreferrer"
            class="projets-button"
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
        </div>
      </div>
      <button class="modal-btn_modal-trigger">
        <img
          src="../image/imgexmpcv.png"
          alt="Miniature"
          class="img_miniature_projets"
        />
      </button>
    </div>
    <section class="Project_modals" data-aos="fade-up">
      <h1>Projet Dynamiser un espace commentaire</h1>
    </section>
    <div class="project">
      <div class="modal-container">
        <div class="overlay_modal-trigger"></div>

        <div class="modal">
          <button class="close-modal_modal-trigger">X</button>
          <p>03/08/2024</p>
          <h1>Mon Projet DynamismeCom</h1>
          <p>Fait avec : JavaScript</p>
          <a
            href="../Dyn.Espc.com/espccom.html"
            target="_blank"
            rel="noopener noreferrer"
            class="projets-button"
          >
            Consulter mon Projet
          </a>
          <a
            href="https://github.com/LLION84/Devoir-c.e.f-ESPACECOMMENTAIRE"
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
        </div>
      </div>
      <button class="modal-btn_modal-trigger">
        <img
          src="../image/IMGESPCOM.png"
          alt="Miniature"
          class="img_miniature_projets"
        />
      </button>
    </div>

    <section class="Formulaire_contact" id="contact" data-aos="fade-up">
      <h2>Me Contacter</h2>
      <form @submit="handleSubmit">
        <input
          v-model="form.name"
          type="text"
          name="from_name"
          placeholder="Ton nom"
          required
        />
        <input
          v-model="form.email"
          type="email"
          name="from_email"
          placeholder="Ton email"
          required
        />
        <textarea
          v-model="form.message"
          name="message"
          placeholder="Ton message"
          required
        ></textarea>
        <button type="submit">Envoyer</button>
      </form>
      <p v-if="isSubmitted" class="confirmation-message">
        Vous avez bien envoyé votre message. Merci !
      </p>
      <p v-if="isError" class="error-message">
        Il manque des informations. Veuillez remplir tous les champs.
      </p>
    </section>
  </main>
  <footer>
    <div class="footer-container">
      <div class="footer-left">
        <p><small>Copyright 2025</small></p>
        <p><small>17/04/2025</small></p>
      </div>
      <div class="reseaux_sociaux">
        <a href="https://www.linkedin.com/in/mohamed-blaise-1a33a9307/">
          <img src="../image/linkedin.png" alt="linkedin" />
        </a>
        <a href="https://www.instagram.com/">
          <img src="../image/instagram.png" alt="instagram" />
        </a>
        <a href="https://github.com/">
          <img src="../image/github.png" alt="github" />
        </a>
      </div>
    </div>
  </footer>
</template>

<script setup>
import AOS from "aos";
import "aos/dist/aos.css";
import emailjs from "emailjs-com";
import { ref } from "vue";

AOS.init();

const form = ref({
  name: "",
  email: "",
  message: "",
});
const isSubmitted = ref(false);
const isError = ref(false);

emailjs.init("awRQk-37qQq35y9ID");

const handleSubmit = (e) => {
  e.preventDefault();

  // Vérification des champs
  if (form.value.name && form.value.email && form.value.message) {
    isSubmitted.value = true;
    isError.value = false;

    form.value.name = "";
    form.value.email = "";
    form.value.message = "";

    emailjs
      .sendForm(
        "service_jlpnhej",
        "template_sop9x8i",
        e.target,
        "awRQk-37qQq35y9ID"
      )
      .then(
        (result) => {
          console.log("Email envoyé avec succès : ", result.text);
        },
        (error) => {
          console.log("Erreur lors de l'envoi : ", error.text);
        }
      );

    // Faire disparaître le message de confirmation après 3 secondes
    setTimeout(() => {
      isSubmitted.value = false;
    }, 3000);
  } else {
    isError.value = true;
    isSubmitted.value = false;
  }
};

document.addEventListener("DOMContentLoaded", () => {
  // Sélectionne tous les boutons et containers
  const modalBtns = document.querySelectorAll(".modal-btn_modal-trigger");
  const modalContainers = document.querySelectorAll(".modal-container");
  const closeButtons = document.querySelectorAll(".close-modal_modal-trigger");

  // Associe chaque bouton à son container (par ordre)
  modalBtns.forEach((btn, index) => {
    const modalContainer = modalContainers[index];
    const closeBtn = closeButtons[index];

    btn.addEventListener("click", () => {
      modalContainer.style.display = "flex";
    });

    closeBtn.addEventListener("click", () => {
      modalContainer.style.display = "none";
    });

    modalContainer.addEventListener("click", (event) => {
      if (!event.target.closest(".modal")) {
        modalContainer.style.display = "none";
      }
    });
  });
});
AOS.init({
  duration: 1000, // Durée de l'animation
  easing: "ease-out", // L'animation commence lentement puis accélère
  once: true, // L'animation se fait une seule fois lors du défilement
});
</script>
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

.logo-scroll {
  position: fixed;
  top: 20px;
  left: 20px;
  z-index: 1000;
  width: 50px;
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

.lien-ancre .link {
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

.lien-ancre .link:hover {
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
.Project_modals {
  text-align: center;
  width: 100%;
  background-color: #3e3128;
  color: #f2e1ca;
  border-radius: 6px;
}
.img_miniature_projets {
  width: 200px;
  padding: 5px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
  border-radius: 10px;
  background-color: #3e3128;
  border: 4px solid #2c221b;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
}

.img_miniature_projets:hover {
  transform: scale(1.1);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
.modal-btn_modal-trigger {
  background: none;
  border: none;
  padding: 0;
}

.modal-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  display: none; /* Masqué par défaut */
  justify-content: center;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.7); /* Fond sombre avec opacité */
  z-index: 9999;
}

.modal-container.active {
  display: flex; /* Affiche le modal lorsqu'il a la classe active */
}
.overlay_modal-trigger {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7); /* Fond sombre */
  z-index: 1;
}
.modal {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 20px;
  background-color: #f2e1ca;
  border-radius: 10px;
  width: 80%;
  max-width: 600px;
  box-shadow: 0px 6px 20px rgba(0, 0, 0, 0.1);
  position: relative;
  z-index: 2;
}
.close-modal_modal-trigger {
  position: absolute;
  top: 10px;
  right: 10px;
  padding: 10px 15px;
  background-color: #e63946;
  color: white;
  border: none;
  border-radius: 50%;
  cursor: pointer;
  font-size: 18px;
  transition: background-color 0.3s ease;
}
.close-modal_modal-trigger:hover {
  background-color: #d32f2f;
}
.modal h1 {
  font-size: 24px;
  margin-bottom: 10px;
  color: #333;
}

.modal p {
  font-size: 16px;
  line-height: 1.5;
  margin: 10px 0;
  color: #555;
}

.projets-button,
.github-link {
  display: inline-flex; /* Utiliser flex pour centrer le texte */
  justify-content: center; /* Centrer horizontalement */
  align-items: center; /* Centrer verticalement */
  padding: 6px 12px;
  border-radius: 8px; /* Forme arrondie pour les deux boutons */
  text-align: center;
  margin-top: 15px; /* Espacement entre les boutons */
  transition: all 0.3s ease;
  min-width: 180px; /* Taille minimale uniforme */
  height: 50px; /* Hauteur uniforme */
  font-size: 16px;
}

/* Bouton CV */
.projets-button {
  background-color: #ad7f58;
  color: #ffffff;
  text-decoration: none;
  font-weight: 600;
  border: 2px solid #ffbe87;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
}

.projets-button:hover {
  background-color: #4d3c2f;
  box-shadow: 0 6px 16px rgba(255, 255, 255, 0.2);
  transform: scale(1.05);
}

/* Lien GitHub */
.github-link {
  background-color: #24292e;
  color: #ffffff;
  text-decoration: none;
  font-weight: bold;
  display: flex;
  align-items: center; /* Centrer l'icône et le texte */
  justify-content: center; /* Centrer l'icône et le texte */
  box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.1);
}

.github-link:hover {
  background-color: #444c56;
  transform: translateY(-1px);
}

/* Icône GitHub */
.github-icon {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  padding: 2px;
  background-color: #ffffff;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  margin-left: 8px; /* Espacement entre l'icône et le texte */
}
.Formulaire_contact {
  width: 100%;
  max-width: 600px;
  margin: 40px auto;
  padding: 25px;
  background-color: #3e3128;
  border-radius: 12px;
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.2);
  color: #f2e1ca;
}
.Formulaire_contact h2 {
  text-align: center;
  margin-bottom: 20px;
  font-size: 24px;
  color: #fbbb8a;
}
.Formulaire_contact form {
  display: flex;
  flex-direction: column;
  gap: 15px;
}
.Formulaire_contact input,
.Formulaire_contact textarea {
  background-color: #28211d;
  border: 2px solid #ad7f58;
  border-radius: 8px;
  padding: 12px;
  font-size: 16px;
  color: #f2e1ca;
  font-family: "Roboto", sans-serif;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
}
.Formulaire_contact input:focus,
.Formulaire_contact textarea:focus {
  border-color: #ffbe87;
  box-shadow: 0 0 8px #ffbe87a8;
  outline: none;
}
.Formulaire_contact textarea {
  resize: vertical;
  min-height: 120px;
}
.Formulaire_contact button[type="submit"] {
  background-color: #ad7f58;
  color: #ffffff;
  border: none;
  border-radius: 8px;
  padding: 14px;
  font-size: 18px;
  font-weight: bold;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.2s ease;
  font-family: "Poppins", sans-serif;
}
.Formulaire_contact button[type="submit"]:hover {
  background-color: #4d3c2f;
  transform: scale(1.03);
}
.confirmation-message {
  color: #4caf50;
  font-weight: bold;
  text-align: center;
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.5s ease, transform 0.5s ease;
  visibility: hidden;
}

.confirmation-message.show {
  opacity: 1;
  transform: translateY(0);
  visibility: visible;
}

.error-message {
  color: #e63946;
  font-weight: bold;
  text-align: center;
}
.not-found {
  text-align: center;
  padding: 50px;
}
img {
  max-width: 500px;
}

footer {
  background-color: #b88c67;
  color: white;
  padding: 20px;
  border-top: 3px solid #8c6a4a; /* Bordure haut uniquement */
}

.footer-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap; /* pour être responsive sur petit écran */
}

.footer-left {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.reseaux_sociaux {
  display: flex;
  gap: 15px;
}

.reseaux_sociaux img {
  width: 30px;
  height: 30px;
  transition: transform 0.3s ease, filter 0.3s ease;
  filter: grayscale(100%) brightness(0.9);
}

.reseaux_sociaux img:hover {
  transform: scale(1.2);
  filter: grayscale(0%) brightness(1.2);
}
</style>

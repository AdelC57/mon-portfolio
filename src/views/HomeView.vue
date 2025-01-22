# HomeView.vue
<template>
  <main>
    <!-- Section Présentation -->
    <section id="presentation" class="section presentation-section">
      <div class="presentation-content">
        <h2>À propos de moi</h2>
        <img
          src="../assets/img/maphoto.png"
          alt="Adel"
          class="profile-photo"
        />
        <div class="text-content">
          <p class="intro">
            Adel, 27 ans | En reconversion vers le Développement Web
          </p>
          <p class="description">
            Actuellement agent de sécurité au Luxembourg, je suis passionné par
            l'univers du développement web et du numérique. Ce qui me fascine
            dans ce domaine, c'est la possibilité de créer à partir d'une page
            blanche et de donner vie à des projets innovants. Ma motivation ?
            Transformer cette passion en profession pour concevoir des solutions
            web, tant pour des projets personnels que pour aider les autres à
            concrétiser leurs idées.
          </p>
        </div>
      </div>
    </section>

    <!-- Section Réalisations -->
    <section id="creations" class="section">
      <h2>Mes Réalisations</h2>
      <div class="projects-grid">
        <div
          v-for="project in projects"
          :key="project.id"
          class="project-card"
          @click="showModal(project)"
        >
          <img :src="project.image" :alt="project.title" />
          <h3>{{ project.title }}</h3>
        </div>
      </div>

      <!-- Modal -->
      <div v-if="selectedProject" class="modal">
        <div class="modal-content">
          <img :src="selectedProject.image" :alt="selectedProject.title" class="modal-image">
          <h2>{{ selectedProject.title }}</h2>
          <p>Date: {{ selectedProject.date }}</p>
          <p>Technologies: {{ selectedProject.technologies }}</p>
          <a :href="selectedProject.link" target="_blank">Voir le projet</a>
          <a :href="selectedProject.github" target="_blank">GitHub</a>
          <button class="close-button" @click="closeModal">Fermer</button>
        </div>
      </div>
    </section>

    <!-- Section Contact -->
    <section id="contact" class="section contact-section">
      <h2>Me contacter</h2>
      <div class="contact-container">
        <form @submit.prevent="handleSubmit" class="contact-form">
          <div class="form-group">
            <label for="name">Nom complet</label>
            <input 
              type="text" 
              id="name" 
              v-model="formData.name" 
              required
              placeholder="Votre nom"
            >
          </div>

          <div class="form-group">
            <label for="email">Adresse e-mail</label>
            <input 
              type="email" 
              id="email" 
              v-model="formData.email" 
              required
              placeholder="votre@email.com"
            >
          </div>

          <div class="form-group">
            <label for="message">Message</label>
            <textarea 
              id="message" 
              v-model="formData.message" 
              required
              placeholder="Votre message"
              rows="6"
            ></textarea>
          </div>

          <button type="submit" class="submit-btn">Envoyer</button>
        </form>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="social-links">
        <a href="https://linkedin.com/" target="_blank" class="social-link">
          <img src="../assets/icons/linkedin.png" alt="LinkedIn">
        </a>
        <a href="https://github.com/" target="_blank" class="social-link">
          <img src="../assets/icons/github.png" alt="GitHub">
        </a>
        <a href="mailto:votre@email.com" class="social-link">
          <img src="../assets/icons/email.png" alt="Email">
        </a>
      </div>
      <div class="footer-bottom">
        <p>&copy; {{ new Date().getFullYear() }} - Tous droits réservés</p>
      </div>
    </footer>
  </main>
</template>

<script>
export default {
  data() {
    return {
      selectedProject: null,
      formData: {
        name: '',
        email: '',
        message: ''
      },
      projects: [
        {
          id: 1,
          title: "Formation",
          image: "../assets/img/maphoto.png",
          description: "Formation Développeur Web et Web Mobile avec le CEF",
          technologies: "HTML, CSS, JavaScript, PHP, MySQL",
          link: "#",
          github: "#",
        },
        {
          id: 2,
          title: "Formation",
          image: "../assets/img/maphoto.png",
          description: "Formation Développeur Web et Web Mobile avec le CEF",
          technologies: "HTML, CSS, JavaScript, PHP, MySQL",
          link: "#",
          github: "#",
        },
        {
          id: 3,
          title: "Formation",
          image: "../assets/img/maphoto.png",
          description: "Formation Développeur Web et Web Mobile avec le CEF",
          technologies: "HTML, CSS, JavaScript, PHP, MySQL",
          link: "#",
          github: "#",
        },
      ],
    };
  },
  methods: {
    showModal(project) {
      this.selectedProject = project;
    },
    closeModal() {
      this.selectedProject = null;
    },
    handleSubmit() {
      console.log('Formulaire soumis:', this.formData)
      this.formData = {
        name: '',
        email: '',
        message: ''
      }
    }
  },
};
</script>

<style>
.section {
  min-height: 100vh;
  padding: 80px 2rem 2rem;
}

/* Styles Présentation */
.presentation-section {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 150px;
}

.presentation-content {
  max-width: 800px;
  text-align: center;
  padding: 2rem;
  margin: 0 25%;
  background-color: white;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
}

.presentation-content h2 {
  margin-top: 2rem;
}

.profile-photo {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  margin: 2rem auto;
  object-fit: cover;
}

.intro {
  font-size: 1.5rem;
  font-weight: bold;
  margin: 1rem 0;
}

.description {
  line-height: 1.6;
  margin: 1rem 0;
}

/* Styles Réalisations */
.projects-grid {
  display: grid;
  grid-template-columns: 1fr;  /* Changement ici pour avoir une seule colonne */
  gap: 3rem;
  max-width: 800px;
  margin: 0 25%;
  padding: 0 1rem;
}

#creations {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 4rem;
}

#creations h2 {
  margin-bottom: 2rem;
  text-align: center;
}

.project-card {
  cursor: pointer;
  border-radius: 8px;
  overflow: hidden;
  background: white;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
  /* Ajout de ces propriétés pour agrandir */
  max-width: 100%;
  min-height: 300px; /* Augmente la hauteur minimale */
}

.project-card img {
  width: 100%;
  height: 300px; /* Augmente la hauteur de l'image */
  object-fit: cover;
}

.project-card h3 {
  padding: 4rem; /* Plus de padding */
  margin: 0;
  text-align: center;
  font-size: 1.5rem; /* Texte plus grand */
}

.project-card:hover {
  transform: scale(1.02);
}

/* Modal Styles */
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-content {
  background: white;
  padding: 2rem;
  border-radius: 8px;
  max-width: 500px;
  width: 90%;
  position: relative;
}

.modal-image {
  width: 100%;
  height: auto;
  margin-bottom: 1rem;
}

.close-button {
  margin-top: 1rem;
  padding: 0.5rem 1rem;
  background: #ff4444;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  width: 100%;
}

.close-button:hover {
  background: #ff0000;
}

/* Contact Section */
.contact-section {
  padding: 4rem 0;
  background-color: #f9f9f9;
}

.contact-container {
  max-width: 800px;
  margin: 0 25%;
  padding: 2rem;
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
}

.contact-section h2 {
  text-align: center;
  margin-bottom: 2rem;
  color: #333;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.form-group label {
  color: #555;
  font-weight: 500;
}

.form-group input,
.form-group textarea {
  padding: 0.8rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
  transition: border-color 0.3s;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #007bff;
}

.submit-btn {
  padding: 1rem;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 4px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s;
}

.submit-btn:hover {
  background-color: #0056b3;
}

/* Footer Styles */
.footer {
  background-color: #333;
  color: white;
  padding: 2rem 0;
  margin-top: 4rem;
}

.social-links {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-bottom: 1.5rem;
}

.social-link img {
  width: 32px;
  height: 32px;
  transition: transform 0.3s;
}

.social-link:hover img {
  transform: translateY(-3px);
}

.footer-bottom {
  text-align: center;
  color: #999;
  font-size: 0.9rem;
}

/* Responsive Design */
@media (max-width: 768px) {
  .presentation-content {
    margin: 0 5%;
    padding: 1rem;
  }
  
  .projects-grid {
    margin: 0 5%;
  }

  .contact-container {
    margin: 0 5%;
    padding: 1rem;
  }

  .social-links {
    gap: 1rem;
  }

  .social-link img {
    width: 28px;
    height: 28px;
  }
}
</style>
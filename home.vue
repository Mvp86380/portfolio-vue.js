<template>
    <div class="home">
      <section id="presentation">
        <h1>{{ prenom }} {{ nom }}</h1>
        <p>Développeur Web passionné par la création d'applications web modernes et dynamiques.</p>
      </section>
      <section id="creations">
        <h2>Mes créations</h2>
        <div class="projects">
          <div v-for="project in projects" :key="project.id" class="project" @click="openModal(project)">
            <img :src="project.image" alt="project.title" />
            <h3>{{ project.title }}</h3>
          </div>
        </div>
        <ProjectModal :project="selectedProject" v-if="showModal" @close="closeModal" />
      </section>
    </div>
  </template>
  <script>
  import ProjectModal from '@/components/ProjectModal.vue';
  export default {
    data() {
      return {
        prenom: 'Bastien',
        nom: 'Schittly',
        projects: [
          { id: 1, title: 'Projet 1', image: 'project1.png', details: {...} },
          { id: 2, title: 'Projet 2', image: 'project2.png', details: {...} },
        ],
        showModal: false,
        selectedProject: null,
      };
    },
    methods: {
      openModal(project) {
        this.selectedProject = project;
        this.showModal = true;
      },
      closeModal() {
        this.showModal = false;
      },
    },
    components: {
      ProjectModal,
    },
  };
  </script>
  <style scoped>
  /* Ajoutez des styles pour la présentation et les projets */
  </style>
  
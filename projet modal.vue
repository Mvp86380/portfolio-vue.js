<template>
    <div class="modal" @click.self="close">
      <div class="modal-content">
        <h2>{{ project.title }}</h2>
        <p>Date de création : {{ project.details.date }}</p>
        <p>Technologies utilisées : {{ project.details.technologies }}</p>
        <a :href="project.details.link" target="_blank">Voir le projet</a>
        <a :href="project.details.github" target="_blank">Code source</a>
        <button @click="close">Fermer</button>
      </div>
    </div>
  </template>
  <script>
  export default {
    props: ['project'],
    methods: {
      close() {
        this.$emit('close');
      },
    },
  };
  </script>
  <style scoped>
  /* Ajoutez des styles pour la modal et son contenu */
  </style>
  
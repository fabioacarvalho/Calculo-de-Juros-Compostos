<template>
  <v-app>
    <v-app-bar
      app
      color="#263238"
      dark
    >
      <div class="d-flex align-center">
        
        <span>Calculadora de Juros Compostos</span>
      </div>

      <v-spacer></v-spacer>

      
    </v-app-bar>

    <v-main>
      <Body/>
    </v-main>
    <v-footer class="pa-1 d-flex justify-center mb-1">
      <span>
        <a class="pa-1" target="_blank" href="https://github.com/fabioacarvalho">
          <img height="40" src="https://www.vectorlogo.zone/logos/github/github-tile.svg" data-canonical-src="https://img.shields.io/badge/github-%23100000.svg?&amp;style=for-the-badge&amp;logo=github&amp;logoColor=white&amp;link=mailto:https://github.com/fabioacarvalho" style="max-width:100%;">
        </a>
        <a class="pa-1" target="_blank" href="https://www.linkedin.com/in/fabio-carvalho-881026142/" rel="nofollow">
          <img height="40" src="https://www.vectorlogo.zone/logos/linkedin/linkedin-tile.svg" data-canonical-src="https://img.shields.io/badge/linkedin-%230077B5.svg?&amp;style=for-the-badge&amp;logo=linkedin&amp;logoColor=white&amp;link=mailto:https://www.linkedin.com/in/fabio-carvalho-881026142/" style="max-width:100%;">
        </a>
      </span>
      <span  class="pa-1 justify-end">Developed by <strong>Fábio Carvalho</strong></span>
    </v-footer>
  </v-app>
  
</template>

<script>
import Body from './components/Body';

export default {
  name: 'App',

  components: {
    Body,
  },

  data: () => ({
    //
  }),
};
</script>

<style >

</style>

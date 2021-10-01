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
    <v-footer>
      Developed by Fábio Carvalho
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

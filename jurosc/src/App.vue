<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        
        <span>Calculo de Juros Compostos</span>
      </div>

      <v-spacer></v-spacer>

      
    </v-app-bar>

    <v-main>
      <Body/>
    </v-main>
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

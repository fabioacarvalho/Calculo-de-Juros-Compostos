<template>
  <v-container fluid>
      <div class="ma-16">
        <v-text-field
          label="Main input"
          :rules="rules"
          hide-details="auto"
        ></v-text-field>
        <v-text-field label="Another input"></v-text-field>
      </div>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      rules: [
        value => !!value || 'Required.',
        value => (value && value.length >= 3) || 'Min 3 characters',
      ],
    }),
  }
</script>

<style >
    

</style>
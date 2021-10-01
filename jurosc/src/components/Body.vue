<template>
  <v-container fluid>
    <v-container v-if="calc == false" fluid>
        <div class="ma-16">
          <v-row >
            <v-col cols="6"  md="6">
              <v-text-field  v-model="valorInicial" type="number" label="Valor Incial"></v-text-field>
            </v-col>
            <v-col cols="6" md="6">
              <v-text-field v-model="aporte" type="number" label="Valor do Aporte Mensal" :rules="rules" hide-details="auto" ></v-text-field>
            </v-col>
            <v-col cols="6" md="6">
              <v-text-field v-model="juros" type="number" label="Taxa de Juros a.a."></v-text-field>
            </v-col>
            <v-col cols="6" md="6">
              <v-text-field v-model="tempo" type="number" label="Tempo Investido (mês)"></v-text-field>
            </v-col>
          </v-row>
        </div>
        <v-container>
          <v-btn color="success" class="ml-10" :disabled="aporte == '' || tempo == '' || juros == ''" @click="calcularJC" >Calcular</v-btn>
        </v-container>
    </v-container>
    <v-container v-if="calc == true" fluid>
      <v-card class="mx-auto" max-width="344" outlined >
        <v-list-item three-line>
          <v-list-item-content>
            <div class="text-overline mb-4">
              Seu retorno
            </div>
            <v-list-item-title type="number" class="text-h5 mb-1">
              {{ total | currency }}
            </v-list-item-title>
            <v-spacer></v-spacer>
            <v-list-item-subtitle>** Essa é apenas uma estimativa.</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-card-actions>
          <v-btn
            outlined rounded text @click="novoCalculo">
            Novo Calculo
          </v-btn>
        </v-card-actions>
      </v-card>
      <br>
      <v-card class="mx-auto pa-5" max-width="450">
        <h2 >Fórmula utilizada para calcular:</h2>
        <v-img class="ma-10 " id="img" width="250" src="../assets/juros-compostos.png"></v-img>
        <p>
          <strong>FV</strong> =  valor futuro <br>
          <strong>PMT</strong> = valor dos aportes mensais <br>
          <strong>n</strong> = número de meses da aplicação <br>
          <strong>i</strong> = taxa fixa.
        </p>
      </v-card>
    </v-container>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      rules: [
        value => !!value || 'Required.',
        value => (value && value.length >= 2) || 'Min 2 characters',
      ],
      valorInicial: '',
      aporte: '',
      juros: '',
      tempo: '',
      total: '',
      calc: false,

    }),
    methods: {
      calcularJC() {
        this.calc = true
        this.total = (this.aporte * ((1 + (this.juros / 100))** (this.juros / 100) - 1)) / (this.juros / 100)
      },
      novoCalculo() {
        this.calc = false
        this.valorInicial = ''
        this.aporte = ''
        this.juros = ''
        this.tempo = ''
        this.total = ''
      }
    }
  }
</script>

<style >


</style>
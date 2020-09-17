<template>
  <div>
    <h1 class='display-1'>坪単価計算</h1>
    <v-container>
      <h2 class='headline'>売買</h2>
      <v-card outlined>
        <v-row>
          <v-col cols='12' md='4'>
            <v-card-text>
              <calculator></calculator>
            </v-card-text>
          </v-col>
          <v-col cols='12' md='4'>
            <v-card-text>
              <calculator></calculator>
            </v-card-text>
          </v-col>
          <v-col cols='12' md='4'>
            <v-card-text>
              <calculator></calculator>
            </v-card-text>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
    <v-container>
      <h2 class='headline'>賃貸</h2>
      <v-card outlined>
        <v-row>
          <v-col cols='12' md='4'>
            <v-card-text>
              <calculator></calculator>
            </v-card-text>
          </v-col>
          <v-col cols='12' md='4'>
            <v-card-text>
            </v-card-text>
            <calculator></calculator>
          </v-col>
          <v-col cols='12' md='4'>
            <v-card-text>
              <calculator></calculator>
            </v-card-text>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
  </div>
</template>

<script>
  import Vue from 'vue'
  import calculator from '~/components/Calculator.vue'

  export default Vue.extend({
    components: {
      calculator
    },
    data: function () {
      return {
        data: {
          price: '',
          area: '',
          unitPrice: '',
        },
      }
    },
  })
</script>
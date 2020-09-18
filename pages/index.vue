<template>
  <div>
    <h1 class='display-1'>坪単価計算表</h1>
    <v-container>
      <v-card outlined>
        <v-toolbar class='headline' color='green darken-2' dark>売買</v-toolbar>
        <v-row v-if="!$vuetify.breakpoint.xs">
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
        <v-col cols='12' md='4' v-else>
          <v-card-text>
            <calculator></calculator>
          </v-card-text>
        </v-col>
      </v-card>
    </v-container>

    <v-container>
      <v-card outlined>
        <v-toolbar class='headline' color='blue-grey' dark>賃貸</v-toolbar>
        <v-row v-if="!$vuetify.breakpoint.xs">
          <v-col cols='12' md='4'>
            <v-card-text>
              <rentCalculator></rentCalculator>
            </v-card-text>
          </v-col>
          <v-col cols='12' md='4'>
            <v-card-text>
              <rentCalculator></rentCalculator>
            </v-card-text>
          </v-col>
          <v-col cols='12' md='4'>
            <v-card-text>
              <rentCalculator></rentCalculator>
            </v-card-text>
          </v-col>
        </v-row>
        <v-col cols='12' md='4' v-else>
          <v-card-text>
            <rentCalculator></rentCalculator>
          </v-card-text>
        </v-col>
      </v-card>
    </v-container>
  </div>
</template>

<script>
  import Vue from 'vue'
  import calculator from '~/components/Calculator.vue'
  import rentCalculator from '~/components/RentCalculator.vue'

  export default Vue.extend({
    components: {
      calculator,
      rentCalculator
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
<style>
  summary {
    margin-left: 1rem;
  }
</style>
<template>
  <div>
    <v-row no-gutters>
      <!-- Chamada de componentes criados separadamente -->
      <v-col md="12">
        <SalesVcard />
        <ChartLineRadialVcard />
      </v-col>
      <v-col> </v-col>
    </v-row>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

// Importando o componente acessando seu devido local de criação
import SalesVcard from "../components/sales-information-vcard.vue";
import ChartLineRadialVcard from "../components/chart-line-radial-vcard.vue";

export default Vue.extend({
  // Criando os componentes
  components: {
    SalesVcard,
    ChartLineRadialVcard,
  },
});
</script>

<style scoped>
</style>
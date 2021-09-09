<template>
  <div>
    <v-row no-gutters>
      <!-- Chamada de componentes criados separadamente -->
      <v-col md="12">
        <SalesVcard />
        <ChartLineVcard />
      </v-col>
      <v-col> </v-col>
    </v-row>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

// Importando o componente acessando seu devido local de criação
import SalesVcard from "../components/sales-information-vcard.vue";
import ChartLineVcard from "../components/chart-line-vcard.vue";

export default Vue.extend({
  // Criando os componentes
  components: {
    SalesVcard,
    ChartLineVcard,
  },
});
</script>

<style scoped>
</style>
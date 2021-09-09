<template>
  <v-col class="container">
    <v-card class="sales-information" elevation="2">
      <v-row>
        <v-col>
          <v-card-title> <h1>Sales</h1> </v-card-title>
          <v-card-subtitle>Welcome to CRM dashboard</v-card-subtitle>
        </v-col>
        <v-btn class="mt-8 mr-6" outlined> <v-icon>mdi-plus</v-icon> Add Widget</v-btn>
      </v-row>
    </v-card>
  </v-col>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({});
</script>

<style scoped>
.container {
  margin-top: 80px;
}
.sales-information {
  font-family: sans-serif;
}
</style>
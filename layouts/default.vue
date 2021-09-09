<template>
  <v-app>
    <!-- Menu De Navegação -->
    <v-navigation-drawer class="menu" width="150" fixed app>
      <v-list class="avatar">
        <v-list-item>
          <v-list-item-avatar>
            <v-img
              src="https://themeselection.com/demo/materio-vuetify-vuejs-admin-template/demo-1/img/1.e2938115.png"
            ></v-img>
          </v-list-item-avatar>
        </v-list-item>
      </v-list>
      <!-- Itens do Menu de Navegação (Os dados necessários para listagem estão sendo criados no 'data') -->
      <v-list class="items">
        <v-list-item v-for="item in items" :key="item.icon">
          <v-list-item-icon>
            <v-btn icon class="t"
              ><v-icon>{{ item.icon }}</v-icon></v-btn
            >
          </v-list-item-icon>
        </v-list-item>
      </v-list>

      <v-list class="arrow">
        <v-list-item>
          <v-btn icon outlined class="t">
            <v-icon>mdi-arrow-collapse-right</v-icon></v-btn
          >
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- Barra de Navegação Superior -->
    <v-app-bar fixed app flat>
      <v-row>
        <v-btn class="search-button" text plain small
          ><v-icon>mdi-magnify</v-icon>Search for anything</v-btn
        >
        <v-spacer></v-spacer>
        <v-btn class="search-button" text plain small
          ><v-icon>mdi-calendar-month</v-icon>Today
          <strong class="date">August 29</strong></v-btn
        >
        <v-spacer></v-spacer>
        <v-btn class="search-button" text small elevation="2"
          >You have <strong>27</strong> new leads
          <v-icon>mdi-hand-pointing-right</v-icon></v-btn
        >
      </v-row>
      <v-btn class="ml-3" icon>
        <v-icon> mdi-bell-outline</v-icon>
        <span class="notify-bell">5</span>
      </v-btn>

      <v-avatar color="primary" size="40">
        <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John" />
      </v-avatar>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      // Dados necessários para listagem do menu
      fixed: false,
      model: 1,
      items: [
        { icon: "mdi-home" },
        { icon: "mdi-tag-arrow-up" },
        { icon: "mdi-account-multiple" },
        { icon: "mdi-view-dashboard" },
        { icon: "mdi-email" },
        { icon: "mdi-folder-multiple" },
        { icon: "mdi-cog" },
      ],
    };
  },
};
</script>

<style>
/* CSS dos componentes do menu e da barra de navegação superior */
.avatar {
  margin-top: 10px;
  margin-left: 40px;
}
.items {
  margin-top: 140px;
  margin-left: 40px;
}
.arrow {
  margin-top: 120px;
  margin-left: 40px;
}
.search-button {
  font-family: sans-serif;
  font-size: x-small;
}
.notify-bell {
  border-radius: 10px;
  font-size: 12px;
  height: 20px;
  letter-spacing: 0;
  min-width: 15px;
  padding: 4px 6px;
  pointer-events: auto;
  position: absolute;
  text-align: center;
  text-indent: 0;
  margin-left: 15px;
  margin-top: -20px;
  background-color: #7d00fc;
  color: #fff;
}
.t:active {
  color: #7d00fc !important;
}
.date {
  color: black;
}
</style>

<template>
  <v-app>
    <v-card flat tile>
      <v-toolbar height="75px" :color="color" dense>
        <v-toolbar-title class="white--text">
          Compradores
        </v-toolbar-title>
        <div class="nav">
          <v-btn text :color="colorIcon">Visão Geral</v-btn>
          <v-btn text :color="colorIcon">Cotações</v-btn>
          <v-btn text class="white--text">Forncedores</v-btn>
        </div>

        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon :color="colorIcon">mdi-magnify</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon :color="colorIcon">mdi-bell-outline</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon :color="colorIcon">mdi-cog-outline</v-icon>
        </v-btn>
      </v-toolbar>
    </v-card>
    <v-content>
      <Dashboard />
    </v-content>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import Dashboard from './modules/views/Dashboard.vue';

export default Vue.extend({
  name: 'App',

  components: {
    Dashboard,
  },

  data: () => ({
    color: '#127C84',
    colorIcon: '#BCF6E6',
  }),
});
</script>

<style>
.nav {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  margin: 0 16px;
}
</style>

<template>
  <v-container>
    <v-row>
      <CardInfo
        v-for="card in cards"
        :key="card.title"
        :icon="card.icon"
        :title="card.title"
        :content="card.content"
      ></CardInfo>
    </v-row>

    <v-card>
      <v-card-title class="grey--text">
        Fornecedores
        <v-spacer></v-spacer>

        <v-text-field
          v-model="search"
          append-icon="mdi-magnify"
          label="Procurar"
          single-line
          hide-details
        ></v-text-field>
      </v-card-title>
      <DataTable />
    </v-card>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue';
import CardInfo from '../components/CardInfo.vue';
import DataTable from '../components/DataTable.vue';

export default Vue.extend({
  name: 'HelloWorld',

  components: {
    CardInfo,
    DataTable,
  },

  data: () => ({
    search: '',
    cards: [
      {
        title: 'Cadastrados',
        content: '39',
        icon: 'mdi-file-outline',
      },
      {
        title: 'Inativos',
        content: '2,696',
        icon: 'mdi-alert-outline',
      },
      {
        title: 'Dúvidas',
        content: '12',
        icon: 'mdi-comment-question-outline',
      },
      {
        title: 'Taxa de resposta',
        content: '78%',
        icon: 'mdi-email-check-outline',
      },
    ],
  }),
});
</script>

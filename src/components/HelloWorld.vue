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
      <v-card-title>
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

      <v-data-table
        :search="search"
        :headers="headers"
        :items="suppliers"
        :items-per-page="5"
        class="elevation-1"
      >
        <template v-slot:item.color="{ item }">
          <v-chip label x-large :color="getColor(item.status)"></v-chip>
        </template>
        <template v-slot:item.status="{ item }">
          <v-chip :color="getColor(item.status)">{{ item.status }}</v-chip>
        </template>
      </v-data-table>
    </v-card>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue';
import CardInfo from './CardInfo.vue';

export default Vue.extend({
  name: 'HelloWorld',

  methods: {
    getColor(status: string) {
      if (status === 'Ativo') return '#91EAD1';
      if (status === 'Inativo') return '#FF5041';
    },
  },

  components: {
    CardInfo,
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
    headers: [
      {
        value: 'color',
        sortable: false,
      },
      {
        text: 'NOME',
        align: 'start',
        sortable: true,
        value: 'name',
      },
      { text: 'COT. A VENCER S/ RESPOSTA', value: 'unansweredQuote' },
      { text: 'COT RESPONDIDAS', value: 'answeredQuote' },
      { text: 'TAXA DE DECLÍNIO', value: 'declinedRate' },
      { text: 'TAXA DE RESPOSTA', value: 'answerRate' },
      { text: 'COTAÇÕES NÃO LIDAS', value: 'unreadQuotes' },
      { text: 'ÚLTIMA ATIVIDADE', value: 'lastActivity' },
      { text: 'STATUS', value: 'status' },
    ],
    suppliers: [
      {
        name: 'Progress Rail Locomotivas do Brasil LTDA',
        unansweredQuote: 21,
        answeredQuote: 21,
        declinedRate: '12.3%',
        answerRate: '11.3%',
        unreadQuotes: 25,
        lastActivity: '29/11/2020 20:00',
        status: 'Ativo',
      },
      {
        name: 'Progress Rail Locomotivas do Brasil LTDA',
        unansweredQuote: 21,
        answeredQuote: 21,
        declinedRate: '12.3%',
        answerRate: '11.3%',
        unreadQuotes: 25,
        lastActivity: '29/11/2020 20:00',
        status: 'Ativo',
      },
      {
        name: 'Progress Rail Locomotivas do Brasil LTDA',
        unansweredQuote: 21,
        answeredQuote: 21,
        declinedRate: '12.3%',
        answerRate: '11.3%',
        unreadQuotes: 25,
        lastActivity: '29/11/2020 20:00',
        status: 'Inativo',
      },
      {
        name: 'Progress Rail Locomotivas do Brasil LTDA',
        unansweredQuote: 21,
        answeredQuote: 21,
        declinedRate: '12.3%',
        answerRate: '11.3%',
        unreadQuotes: 25,
        lastActivity: '29/11/2020 20:00',
        status: 'Inativo',
      },
    ],
  }),
});
</script>

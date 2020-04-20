<template>
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
</template>

<script>
import Vue from 'vue';

export default Vue.extend({
  methods: {
    getColor(status) {
      if (status === 'Ativo') return '#91EAD1';
      if (status === 'Inativo') return '#FF5041';
    },
  },

  data: () => ({
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

<style></style>

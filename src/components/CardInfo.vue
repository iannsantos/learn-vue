<template>
  <div class="card">
    <v-row>
      <v-icon :color="color" size="48" class="icon">{{ icon }}</v-icon>
      <v-col>
        <p class="card-title">{{ title }}</p>
        <p class="card-content">{{ content }}</p>
      </v-col>
    </v-row>
  </div>

  <!-- <v-card class="d-inline-block">
    <v-row>
      <v-img
        height="48"
        width="38"
        src="https://cdn.vuetifyjs.com/images/cards/store.jpg"
      ></v-img>
      <v-col cols="auto">
        <v-card-title>Cadastrados</v-card-title>
        <v-card-text>
          39
        </v-card-text>
      </v-col>
    </v-row>
  </v-card> -->
</template>

<script>
import Vue from 'vue';

export default Vue.extend({
  props: ['icon', 'title', 'content'],
  data: () => ({
    size: 48,
    color: '#11AAA4',
  }),
});
</script>

<style>
.card {
  background: #ffffff 0% 0% no-repeat padding-box;
  box-shadow: 4px 4px 8px #1e1e1e14;
  border: 1px solid #efeff0;
  border-radius: 4px;

  padding: 12px 24px;
  margin: 0 8px;
  min-width: 20vw;
}

.card-title {
  text-align: left;
  letter-spacing: 0px;
  color: #676767;
}

.card-content {
  text-align: left;
  font-size: 24px;
  font-weight: bold;
  color: #333333;
}
</style>

<template>
  <v-card class="mb-8 mx-auto" :width="width" outlined>
    <v-list-item two-line>
      <v-list-item-avatar>
        <v-icon :size="size" :color="color">{{ icon }}</v-icon>
      </v-list-item-avatar>
      <v-list-item-content>
        <v-list-item-subtitle>{{ title }}</v-list-item-subtitle>
        <v-list-item-title class="headline">{{ content }}</v-list-item-title>
      </v-list-item-content>
    </v-list-item>
  </v-card>
</template>

<script>
import Vue from 'vue';

export default Vue.extend({
  props: ['icon', 'title', 'content'],
  data: () => ({
    size: 40,
    color: '#11AAA4',
    width: '20%',
  }),
});
</script>

<style></style>

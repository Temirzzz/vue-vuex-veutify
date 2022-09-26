<template>
  <v-dialog
    max-width="600"
    v-model="$store.getters.getDialogVisible"
    @click:outside="$store.commit('hideDialog')"
  >
    <v-card>
      <v-card-title>{{ full_title }}</v-card-title>
      <v-card-text>
        <v-img :src="$store.getters.getCurrentPhoto.url" />
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  computed: {
    full_title() {
      return `Название фотографии - ${this.$store.getters.getCurrentPhoto.title}`;
    },
  },
};
</script>

<style lang="scss" scoped></style>

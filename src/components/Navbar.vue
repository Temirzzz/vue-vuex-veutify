<template>
  <v-container fluid>
    <v-app-bar color="primary" dark>
      <v-spacer />
      <v-btn outlined class="ml-3 navbar__btn">
        <router-link to="/">Главная</router-link>
      </v-btn>
      <v-btn outlined class="ml-3 navbar__btn">
        <router-link to="/photo">Фотографии</router-link>
      </v-btn>
    </v-app-bar>
  </v-container>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.container {
  padding: 0;
}
.navbar__btn {
  border: none;
  a {
    color: #fff;
    text-decoration: none;
  }
}
</style>

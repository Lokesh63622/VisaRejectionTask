<template>
  <v-app>
    <NavBar />
    <v-main class="mx-7">
      <router-link to="/"></router-link>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
import NavBar from "./views/NavBar.vue";

export default {
  name: "App",

  data: () => ({
    //
  }),
  components: {
    NavBar,
  },
};
</script>
<style>
* {
  text-decoration: none !important;
}
</style>

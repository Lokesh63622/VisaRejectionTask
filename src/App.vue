<template>
  <v-app>
    <NavBar />
    <v-main class="mx-7">
    
    <router-link to="/"></router-link>
    <router-view/>
    <!-- <MainContent/> -->
    </v-main>
  </v-app>
</template>

<script>
import NavBar from "./views/NavBar.vue";
// import MainContent from "./views/MainContent.vue";
export default {
  name: "App",

  data: () => ({
    //
  }),
  components: {
    NavBar,
  //  MainContent,
    
  },
};
</script>
<style>
*{
  text-decoration: none !important;
}
</style>
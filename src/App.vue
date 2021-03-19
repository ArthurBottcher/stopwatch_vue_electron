<template>
  <v-app style="-webkit-app-region: drag"> <Home /> </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import Home from "./views/Home.vue";
export default Vue.extend({
  name: "App",

  components: {
    Home,
  },

  data: () => ({
    //
  }),
});
</script>
<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Share+Tech+Mono");

* {
  padding: 0;
  margin: 0;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  font-family: "Share Tech Mono", sans-serif;
  overflow-y: auto !important;
}
</style>

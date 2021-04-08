<template>
  <v-app>
    <Navbar />
    <Sidebar />
    <v-content>
      <router-view />
    </v-content>
  </v-app>
</template>

<script>
import Navbar from "@/components/Header/Navbar.vue";
import Sidebar from "@/components/Header/Sidebar.vue";
export default {
  components: {
    Navbar,
    Sidebar,
  },
};
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  background-color: #f7f7f7;
  color: #2c3e50;
}
</style>

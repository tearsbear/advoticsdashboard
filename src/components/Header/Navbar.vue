<template>
  <v-app-bar app clipped-left color="white" elevation="2">
    <v-toolbar-title>
      <img src="../../assets/logo.jpg" width="120" class="mt-2" alt="" />
    </v-toolbar-title>

    <p class="powered-by-text grey--text font-weight-medium mt-7 ml-2">
      powered by
    </p>
    <img src="../../assets/logo.jpg" class="mt-2 ml-1" width="80" alt="" />

    <v-spacer></v-spacer>

    <div class="menu-link">
      <h4 class="grey--text">Username</h4>
      <p class="grey--text">Company Name</p>
    </div>

    <v-btn icon>
      <img src="../../assets/icons/profile.svg" width="25" alt="" />
    </v-btn>

    <v-btn icon>
      <img src="../../assets/icons/logout.png" width="20" alt="" />
    </v-btn>
  </v-app-bar>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style scoped>
.powered-by-text {
  font-size: 13px;
}

.menu-link {
  margin-top: 15px;
  margin-right: 5px;
}

.menu-link h4 {
  font-size: 14px;
}
.menu-link p {
  font-size: 10px;
}
</style>
<template>
  <v-navigation-drawer
    app
    v-model="drawer"
    mini-variant
    permanent
    clipped
    elevation="2"
    color="white"
    class="mt-100"
  >
    <v-list>
      <v-list-item>
        <v-list-item-icon>
          <v-icon>mdi-text</v-icon>
        </v-list-item-icon>
      </v-list-item>
      <v-list-item style="background-color: #d2d2d2 !important">
        <v-list-item-icon>
          <img
            class="white"
            style="padding: 2px; border-radius: 5px"
            src="../../assets/icons/dashboard.svg"
            alt=""
          />
        </v-list-item-icon>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  name: "Sidebar",
  data() {
    return {
      drawer: true,
    };
  },
};
</script>
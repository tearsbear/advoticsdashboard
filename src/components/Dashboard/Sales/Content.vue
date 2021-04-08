<template>
  <div>
    <v-card class="mt-3" elevation="1" outlined max-width="380">
      <v-list-item class="grow">
        <v-list-item-content>
          <v-list-item-title class="grey--text font-weight-medium"
            >Sales Turnover</v-list-item-title
          >
        </v-list-item-content>

        <v-row align="center" justify="end">
          <v-icon class="mr-1 grey--text">mdi-dots-vertical</v-icon>
        </v-row>
      </v-list-item>
      <v-list-item class="mt-3 pb-5">
        <v-row align="center" justify="start">
          <h1 class="ml-3" style="color: #424242">Rp {{ getData[0].value }}</h1>
          <p
            style="font-size: 13px"
            class="grey--text font-weight-medium mt-n1 ml-2"
          >
            <v-icon class="red--text">{{ getData[0].icon }}</v-icon>
            <b class="red--text">{{ getData[0].percentage }}%</b> Last period in
            products sold
          </p>
        </v-row>
        <v-row align="center" class="mt-n7" justify="end">
          <img
            class="mr-10"
            src="../../../assets/icons/cart.svg"
            width="80"
            alt=""
          />
        </v-row>
      </v-list-item>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "Content",
  props: ["salesData"],
  data() {
    return {
      getData: this.salesData,
    };
  },
};
</script>
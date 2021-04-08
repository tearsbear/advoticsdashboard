<template>
  <div class="mt-3" style="background-color: #37b04c; height: 50px">
    <v-row>
      <v-col class="text-left">
        <h3 class="ml-3 white--text">MARKET INSIGHTS</h3>
      </v-col>
      <v-col class="white--text">
        <v-row>
          <v-col class="text-right">
            <img
              width="25"
              style="margin-right: -20px"
              src="../../../assets/icons/bulb.png"
              alt=""
            />
          </v-col>
          <v-col cols="3">
            <p class="text-decoration-underline">Click Here for Help</p>
          </v-col>
          <v-col cols="1">
            <v-icon class="white--text" style="margin-left: -15px"
              >mdi-chevron-up</v-icon
            >
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "Banner",
};
</script>
<template>
  <div class="mt-2">
    <v-container fluid>
      <v-row>
        <v-col>
          <h1 style="text-align: left; color: #707070c4">Dashboard</h1>
        </v-col>
        <v-col class="text-right">
          <!-- period option component -->
          <Datepicker />
          <!-- period option component -->
        </v-col>
      </v-row>

      <!-- insight banner component -->
      <Banner />
      <!-- insight banner component -->

      <!-- sales turnover component -->
      <Content :salesData="salesData" />
      <!-- sales turnover component -->

      <v-row class="mt-1">
        <v-col cols="6">
          <AverageChart />
        </v-col>
        <v-col>
          <v-card outlined elevation="1">
            <v-list-item class="grow">
              <h4 class="font-weight-medium" style="color: #4d4f5c">
                BEST SELLING SKU
              </h4>

              <v-row align="center" justify="end">
                <v-icon class="mr-1 grey--text">mdi-dots-vertical</v-icon>
              </v-row>
            </v-list-item>

            <v-container>
              <BestSelling :bestSellingData="bestSellingData" />
            </v-container>
          </v-card>
        </v-col>
        <v-col>
          <v-card outlined elevation="1">
            <v-list-item class="grow">
              <h4 class="font-weight-medium" style="color: #4d4f5c">
                TOP COMPETITOR SKU
              </h4>
              <v-row align="center" justify="end">
                <v-icon class="mr-1 grey--text">mdi-dots-vertical</v-icon>
              </v-row>
            </v-list-item>
            <v-container>
              <CompetitorSelling
                :competitorSellingData="competitorSellingData"
              />
            </v-container>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
//components
import Datepicker from "@/components/Dashboard/Period/Datepicker.vue";
import Content from "@/components/Dashboard/Sales/Content.vue";
import Banner from "@/components/Dashboard/Insight/Banner.vue";
import AverageChart from "@/components/Dashboard/Average/AverageChart.vue";
import BestSelling from "@/components/Dashboard/Selling/BestSelling.vue";
import CompetitorSelling from "@/components/Dashboard/Selling/CompetitorSelling.vue";

//dummy data
import dataSales from "@/data/Sales/data.js";
import dataSelling from "@/data/Selling/bestSelling.js";
import dataCompetitor from "@/data/Selling/competitorSelling.js";

export default {
  name: "Home",
  components: {
    Datepicker,
    Content,
    Banner,
    AverageChart,
    BestSelling,
    CompetitorSelling,
  },
  data() {
    return {
      salesData: dataSales,
      bestSellingData: dataSelling,
      competitorSellingData: dataCompetitor,
    };
  },
};
</script>

<style scoped>
</style>

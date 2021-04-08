<template>
  <div>
    <v-card outlined elevation="1" height="474">
      <v-list-item class="grow">
        <h4 class="font-weight-medium" style="color: #4d4f5c">
          AVERAGE PURCHASE VALUE
        </h4>

        <v-row align="center" justify="end">
          <v-select
            style="max-width: 150px"
            label="Last 6 month"
            dense
            outlined
            class="mt-7"
          ></v-select>
          <v-icon class="mr-1 grey--text">mdi-dots-vertical</v-icon>
        </v-row>
      </v-list-item>
      <center>
        <apexchart
          class="mt-2"
          type="line"
          height="350"
          :options="chartOptions"
          :series="series"
        >
        </apexchart>
      </center>
    </v-card>
  </div>
</template>
<script>
export default {
  name: "AverageChart",
  data() {
    return {
      series: [
        {
          name: "Average Purchase Value",
          type: "column",
          data: [440, 505, 414, 671, 227, 413, 201, 352, 752, 320, 257, 160],
        },
        {
          name: "Unit per Transaction",
          type: "line",
          data: [23, 42, 35, 27, 43, 22, 17, 31, 22, 22, 12, 16],
        },
      ],
      chartOptions: {
        colors: ["#37B04C", "#FFE854"],
        fill: {
          colors: ["#37B04C", "#FFE854"],
        },
        markers: {
          colors: ["#37B04C", "#37B04C"],
        },
        chart: {
          height: 350,
          type: "line",
        },
        stroke: {
          width: [0, 4],
        },
        title: {
          text: "",
        },
        dataLabels: {
          enabled: true,
          enabledOnSeries: [1],
          style: {
            colors: ["#37B04C", "#37B04C"],
          },
        },
        labels: [
          "01 Jan 2001",
          "02 Jan 2001",
          "03 Jan 2001",
          "04 Jan 2001",
          "05 Jan 2001",
          "06 Jan 2001",
          "07 Jan 2001",
          "08 Jan 2001",
          "09 Jan 2001",
          "10 Jan 2001",
          "11 Jan 2001",
          "12 Jan 2001",
        ],
        xaxis: {
          type: "datetime",
        },
        yaxis: [
          {
            title: {
              text: "",
            },
          },
          {
            opposite: true,
            title: {
              text: "Chart",
            },
          },
        ],
      },
    };
  },
};
</script>
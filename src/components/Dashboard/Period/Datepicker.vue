<template>
  <div>
    <v-menu transition="slide-y-transition" :close-on-click="false" bottom>
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          class="grey--text font-weight-bold rounded-0 text-capitalize"
          color="white"
          dark
          height="45"
          v-bind="attrs"
          v-on="on"
        >
          <v-icon class="mr-1">mdi-calendar</v-icon>
          <span class="mr-5">Period</span>
          11 September 2018 - 14 September 2018
          <v-icon>mdi-chevron-down</v-icon>
        </v-btn>
      </template>
      <v-card outlined elevation="1" width="650">
        <v-list-item class="grow">
          <v-icon class="grey--text">mdi-calendar</v-icon>
          <h4 class="font-weight-bold ml-2 grey--text" style="color: #4d4f5c">
            Period
          </h4>

          <v-row align="center" justify="end">
            <v-chip class="ma-2 green--text">{{ pickerText }}</v-chip>
            <v-btn @click="resetDate()" icon>
              <v-icon class="mr-1 grey--text">mdi-close</v-icon>
            </v-btn>
          </v-row>
        </v-list-item>

        <v-row>
          <v-col cols="3">
            <v-list flat>
              <v-list-item-group v-model="selectedItem" color="#37B04C">
                <v-list-item
                  v-for="(item, i) in period"
                  @click.stop.prevent
                  @click="changeDate(item.interval)"
                  :key="i"
                >
                  <v-list-item-content style="border-bottom: 1px solid #d2d2d2">
                    <v-list-item-title v-text="item.text"></v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
              <v-btn
                class="ma-4 white--text"
                width="115"
                elevation="0"
                color="#37B04C"
                >Apply</v-btn
              >
            </v-list>
          </v-col>
          <v-col class="mr-3">
            <v-date-picker
              v-model="picker"
              range
              full-width
              color="#37B04C"
            ></v-date-picker>
          </v-col>
        </v-row>
      </v-card>
    </v-menu>
  </div>
</template>

<script>
export default {
  name: "Datepicker",
  data() {
    return {
      selectedItem: null,
      period: [
        { text: "Today", interval: 0 },
        { text: "Yesterday", interval: 1 },
        { text: "Last 7 days", interval: 7 },
        { text: "Last 30 days", interval: 30 },
        { text: "This month", interval: 31 },
        { text: "Custom", interval: null },
      ],
      picker: new Date().toISOString().substr(0, 10),
      pickerText: new Date().toISOString().substr(0, 10),
    };
  },
  methods: {
    changeDate(getInterval) {
      //get todays date
      const today = new Date();
      //get yesterday date
      const olday = new Date(today);

      //if period is today
      //change datepicker date to current date
      if (getInterval == 0) {
        this.picker = new Date().toISOString().substr(0, 10);
        this.pickerText = new Date().toISOString().substr(0, 10);

        //if period is yesterday
        //change datepicker date to yesterday date
      } else if (getInterval == 1) {
        //todays date - 1 day
        olday.setDate(olday.getDate() - 1);
        this.picker = olday.toISOString().substr(0, 10);
        this.pickerText = olday.toISOString().substr(0, 10);

        //if period is last 7 days
        //change datepicker date to 7 days from now
      } else if (getInterval == 7) {
        //todays date - 7 day
        olday.setDate(olday.getDate() - 7);
        this.picker = [
          new Date().toISOString().substr(0, 10),
          olday.toISOString().substr(0, 10),
        ];
        this.pickerText =
          new Date().toISOString().substr(0, 10) +
          " to " +
          olday.toISOString().substr(0, 10);

        //if period is last 30 days
        //change datepicker date to 30 days from now
      } else if (getInterval == 30) {
        //todays date - 30 day
        olday.setDate(olday.getDate() - 30);
        this.picker = [
          new Date().toISOString().substr(0, 10),
          olday.toISOString().substr(0, 10),
        ];
        this.pickerText =
          new Date().toISOString().substr(0, 10) +
          " to " +
          olday.toISOString().substr(0, 10);

        //if period is this month
        //change datepicker to select all date on current month
      } else if (getInterval == 31) {
        const date = new Date();
        const firstDay = new Date(date.getFullYear(), date.getMonth() + 1, -28);
        const lastDay = new Date(date.getFullYear(), date.getMonth() + 1, 1);
        this.picker = [
          firstDay.toISOString("dd-mm-yyyy").substr(0, 10),
          lastDay.toISOString("dd-mm-yyyy").substr(0, 10),
        ];
        this.pickerText =
          firstDay.toISOString("dd-mm-yyyy").substr(0, 10) +
          " to " +
          lastDay.toISOString("dd-mm-yyyy").substr(0, 10);
      } else {
        this.picker = new Date().toISOString().substr(0, 10);
      }
    },
    resetDate() {
      this.picker = new Date().toISOString().substr(0, 10);
      this.selectedItem = null;
    },
  },
};
</script>
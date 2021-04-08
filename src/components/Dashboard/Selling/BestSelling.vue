<template>
  <div>
    <v-card
      v-for="(item, i) in getData"
      :key="i"
      outlined
      :color="item.cardBg"
      :class="item.cardSpace"
      :height="item.cardHeight"
    >
      <div class="d-flex flex-no-wrap">
        <img
          :width="item.imgWidth"
          :height="item.imgHeight"
          class="rounded"
          :src="item.imgSrc"
        />
        <div :class="item.textSpace">
          <v-card-title>{{ item.name }}</v-card-title>

          <v-card-subtitle>
            Rp {{ item.price }} [{{ item.sold }}]
          </v-card-subtitle>
        </div>
      </div>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "BestSelling",
  props: ["bestSellingData"],
  data() {
    return {
      getData: this.bestSellingData,
    };
  },
};
</script>
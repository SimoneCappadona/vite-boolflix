<script>
import appCard from "./appCard.vue";

export default {
  components: { appCard },
  props: { films: Array, tvSeries: Array},
};
</script>

<template>
  <div class="container mt-5">
    <div class="row g-2">
      <appCard v-for="film in films" :ikea="film"></appCard>
    </div>
    <div class="row g-2">
      <appCard v-for="serie in tvSeries" :ikea="serie"></appCard>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>

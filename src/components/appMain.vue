<script>
import appCard from "./appCard.vue";

export default {
  components: { appCard },
  props: { films: Array,},
};
</script>

<template>
  <div class="container mt-5">
    <div class="row g-2">
      <appCard v-for="film in films" :films="film"></appCard>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>

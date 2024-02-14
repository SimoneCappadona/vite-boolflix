<script>
export default {
  props: { films: Object },
};
</script>

<template>
  <div class="col-3">
    <img
      :src="'https://image.tmdb.org/t/p/w342' + films.poster_path"
      alt=""
      class="object-fit-fill rounded"
    />
  </div>
</template>

<style lang="scss" scoped></style>

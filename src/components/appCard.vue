<script>
export default {
  props: {
    films: Object,},
};
</script>

<template>
  <div class="col-3">
    <img
      :src="'https://image.tmdb.org/t/p/w342' + films.poster_path"
      alt=""
      class="object-fit-fill rounded"
    />
    <h1 class="ftitle">{{ films.original_title }}</h1>
    <p class="ftheme">{{ films.overview }}</p>
    <p class="flang">{{ films.original_language }}</p>
    <p class="fvote">{{ films.vote_average }}</p>
  </div>
</template>

<style lang="scss" scoped></style>

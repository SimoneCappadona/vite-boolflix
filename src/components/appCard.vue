<script>
export default {
  methods: {
    getVote(vote) {
      return Math.ceil(vote / 2);
    },
    getLang(language) {
      return;
    },
    nullImg(imgnull) {
      return;
    },
  },
  props: {
    films: Object,
  },
};
</script>

<template>
  <div class="col-3">
    <div class="cardcontainer">
      <div class="filmimg">
        <img
          :src="'https://image.tmdb.org/t/p/w342' + films.poster_path"
          alt=""
          class="object-fit-fill rounded"
        />
      </div>
      <div class="hoveredtext">
        <h1 class="ftitle text-center">{{ films.original_title }}</h1>
        <p class="ftheme text-center">{{ films.overview }}</p>
        <p class="flang text-center p-2 d-flex">Language: <img src="../assets/img/English_language.png" class="langimg mx-2">{{ films.original_language }}</p>
        <p class="fvote text-center">
          Vote:<i
            :class="
              i <= getVote(films.vote_average)
                ? 'fa-solid fa-star fa-lg'
                : 'fa-regular fa-star fa-lg'
            "
            style="color: #ffd43b"
            v-for="i in 5"
          ></i>
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/partials/variables.scss" as *;
.ftitle {
  padding: 10px;
  font-size: 30px;
}
.ftheme {
  padding: 10px;
}
.ftitle,
.ftheme,
.flang,
.fvote {
  color: white;
}
.hoveredtext {
  display: none;
  background-color: rgba($color: #000000, $alpha: 0.5);
  border-radius: 10px;
}
.cardcontainer:hover {
  .filmimg {
    display: none;
  }
  .hoveredtext {
    display: block;
  }
}
.langimg{
  width: 20%;
}
</style>

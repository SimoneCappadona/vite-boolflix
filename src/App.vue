<script>
import appMain from "./components/appMain.vue";
import appHeader from "./components/appHeader.vue";
import appFooter from "./components/appFooter.vue";
import axios from "axios";

export default {
  data() {
    return {
      films: [],
      tvSeries: [],  
    };
  },
  methods: {
    getText(textReceived){
      this.pippo(textReceived),
      this.pluto(textReceived)
    },
    pippo(text) {
      axios
        .get(
          `https://api.themoviedb.org/3/search/movie?api_key=97bba07d2cc88a3bb39b834bc6ba35b8&query=${text}`
        )
        .then((result) => {
          this.films = result.data.results.map((film)=>{
            return{
              title: film.original_title,
              poster:film.poster_path,
              theme: film.overview,
              lang: film.original_language,
              vote: film.vote_average,
            }
          });
        });
    },
    pluto(text) {
      axios
        .get(
          `https://api.themoviedb.org/3/search/tv?api_key=97bba07d2cc88a3bb39b834bc6ba35b8&query=${text}`
        )
        .then((response) => {
          this.tvSeries = response.data.results.map((serie)=>{
            return{
              title:serie.original_name,
              poster:serie.poster_path,
              theme:serie.overview,
              lang:serie.original_language,
              vote:serie.vote_average,
            }
          });
        });
    },
   
  },
  components: { appHeader, appMain, appFooter },
};
</script>
<template>
  <appHeader @onClick="getText"></appHeader>
  <appMain
    :films="films"
    :tvSeries="tvSeries"
  ></appMain>
  <appFooter></appFooter>
</template>

<style lang="scss">
@use "./assets/general.scss";
</style>

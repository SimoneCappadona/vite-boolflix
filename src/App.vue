<script>
import appMain from "./components/appMain.vue";
import appHeader from "./components/appHeader.vue";
import appFooter from "./components/appFooter.vue";
import axios from "axios";

export default {
  data() {
    return {
      films: [],
         
    };
  },
  methods: {
    pippo(text) {
        axios
        .get(
          `https://api.themoviedb.org/3/search/movie?api_key=97bba07d2cc88a3bb39b834bc6ba35b8&query=${text}`
          )
          .then((result) => {
            this.films = result.data.results; 
          }); 
  },
    },
    components: { appHeader, appMain, appFooter },
  };
</script>
<template>
  <appHeader @onClick="pippo"></appHeader>
  <appMain :films="films"></appMain>
  <appFooter></appFooter>
</template>

<style lang="scss">
@use "./assets/general.scss";
</style>

<script>
export default {
  data() {
    return {
      filmSearch:''
    }
    
  }, 
  
  emits:['onClick'],
  props:{films: Array}
};
</script>
<template>
  <div class="header">
    <div class="d-flex p-3 justify-content-between">
      <h1 class="pagetitle">BOOLFLIX</h1>
      <div class="input-group mb-3">
        <input type="search" class="form-control" placeholder="Cerca" aria-label="Cerca" aria-describedby="button-addon2 " v-model="filmSearch"/>
        <button class="btn btn-outline-secondary" type="search" id="button-addon2" @click="$emit('onClick',filmSearch)">
          Cerca
        </button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/partials/variables.scss" as *;
.header {
  height: 80px;
  max-width: 100%;
  background-color: $headerbg;
  box-shadow: 0px 5px 5px ;
}
.pagetitle {
  color: $font-red;
}
.input-group {
  width: 15%;
}
</style>

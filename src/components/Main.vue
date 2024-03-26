<script>
import { store } from "../data/store";
import Card from "./partials/Card.vue";
export default {
  data() {
    return {
      store,
      inputSearch: "",
      selectSearch: "",
    };
  },
  components: {
    Card,
  },
  mounted() {},
};
</script>

<template>

      <div class="d-flex justify-content-center align-items-center">
        <div class="d-flex">
        
          <input
            class="form-control"
            type="text"
            placeholder="Select Character"
            aria-label=""
          />
      
          <select class="form-select" aria-label="Default select example">
            <option selected>Select Status</option>
            <option value="1">Alive</option>
            <option value="2">Dead</option>
            <option value="3">Unknown</option>
          </select>
      
        </div>
        <div>
          <div class="btn btn-info">Search</div>
          <div class="btn btn-warning">Reset</div>
        </div>
      </div>

  <div class="wrapper d-flex">
    <div class="container d-flex flex-around">
      <div class="row row-cols-3 d-flex">
        <Card
          class="col m-3 mb-5"
          v-for="card in store.cardList"
          :key="card.id"
          :cardName="card.name"
          :cardStatus="card.status"
          :cardGender="card.gender"
          :cardSpecies="card.species"
          :cardImage="card.image"
          :cardLocation="card.location.name"
        />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.row {
  justify-content: center;
}
</style>
<script>
import { store } from "./data/store.js";
import axios from "axios";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
export default {
  components: {
    Header,
    Main,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getApi() {
      axios
        .get(this.store.apiUrl)
        .then((res) => {
          console.log("nella function", res.data.results);
          this.store.cardList = res.data.results;
          console.log("nello store", this.store.cardList[0]);
        })
        .catch((error) => console.log(error));
    },
  },

  mounted() {
    this.getApi();
  },
};
</script>

<template>
  <div class="wrapper">
    <Header /><br />
    <Main />
  </div>
</template>

<style lang="scss" scoped>
@use "src/style.css"
</style>
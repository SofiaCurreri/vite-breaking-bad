<script>
import AppHeader from "./components/AppHeader.vue";
import CardList from "./components/CardList.vue";

import cardType from "./components/_cardtype.js";
import axios from "axios";

export default {
  data() {
    return {
      cardType,
      oneTypeCards: [],
    };
  },
  components: { AppHeader, CardList },

  created() {
    axios
      .get(" https://db.ygoprodeck.com/api/v7/cardinfo.php?type=Spell%20Card")
      .then((response) => {
        console.log(response);
        this.oneTypeCards = response.data;
      });
  },
};
</script>

<template>
  <AppHeader />

  <main class="d-flex align-items-end">
    <div class="container">
      <select id="card-type" class="mt-3">
        <option v-for="singleType in cardType" :value="singleType">
          {{ singleType }}
        </option>
      </select>
      <CardList />
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  height: 170vh;
  background-color: rgb(212, 143, 56);
}

.container {
  background-color: white;
  height: 90%;
}
</style>

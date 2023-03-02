<script>
import axios from "axios";

export default {
  data() {
    return {
      cards: [],
    };
  },

  created() {
    axios
      .get(" https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0")
      .then((response) => {
        console.log(response);
        this.cards = response.data;
      });
  },
};
</script>

<template>
  <div class="row row-cols-5 justify-content-center p-3">
    <div class="col text-center card m-3" v-for="card in cards.data">
      <img :src="card.card_images[0].image_url" alt="" />
      <div class="p-2">
        <h4>{{ card.name }}</h4>
        <p>{{ card.type }}</p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  width: calc(100% / 5 - 2rem);
  background-color: rgb(212, 143, 56);
  & h4 {
    color: white;
  }

  & img {
    width: 100%;
  }
}

.row > * {
  padding-left: 0;
  padding-right: 0;
}
</style>

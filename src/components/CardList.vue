<script>
import axios from "axios";

export default {
  data() {
    return {
      cards: [],
    };
  },

  create() {
    axios
      .get(" https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0")
      .then((response) => {
        console.log(response);
      });
  },
};
</script>

<template></template>

<style lang="scss" scoped></style>

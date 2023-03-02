<script>
import AppHeader from "./components/AppHeader.vue";
import CardList from "./components/CardList.vue";

import cardType from "./components/_cardtype";

export default {
  data() {
    return {
      cardType,
    };
  },
  components: { AppHeader, CardList },
};
</script>

<template>
  <AppHeader />

  <main class="d-flex align-items-end">
    <div class="container">
      <select id="card-type">
        <option v-for="singleType in cardType" value="">
          {{ singleType }}
        </option>
      </select>
      <CardList />
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  height: 100vh;
  background-color: rgb(212, 143, 56);
}

.container {
  background-color: white;
  height: 90%;
}
</style>

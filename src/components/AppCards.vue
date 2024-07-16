<template>
  <main>
    <h1>This is a cards container</h1>
    <section>
      <!-- <AppSingleCard /> -->
      <AppSingleCard
        v-if="cardsArray && cardsArray.pokemon_species"
        v-for="pokemon in cardsArray.pokemon_species"
        :key="pokemon.name"
        :pokemon="pokemon"
      />
    </section>
  </main>
</template>
<script>
import AppSingleCard from "./AppSingleCard.vue";

export default {
  components: {
    AppSingleCard,
  },
  props: {
    cardsArray: Object,
  },
  data() {
    return {
      newCard: {
        name: "",
      },
    };
  },
};
</script>

<style scoped>
h1 {
  text-align: center;
  padding-top: 30px;
}
main {
  background-color: rgb(234, 233, 233);
  width: 100%;
  height: 100%;
}
</style>

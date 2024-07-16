<template>
  <section class="cardContainer">
    <AppSingleCard
      v-if="cardsArray && cardsArray.pokemon_species"
      v-for="pokemon in pokemonIdProcessor"
      :key="pokemon.id"
      :pokemon="pokemon"
    />
  </section>
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
  computed: {
    pokemonIdProcessor() {
      if (
        !this.cardsArray.pokemon_species ||
        this.cardsArray.pokemon_species.length === 0
      ) {
        return [];
      }

      return this.cardsArray.pokemon_species.map((pokemon) => {
        const id = pokemon.url.split("/").slice(-2, -1)[0];
        return { ...pokemon, id };
      });
    },
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
.cardContainer {
  /* display: flex;
  flex-wrap: wrap; */
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));

  row-gap: 2.5rem;
  column-gap: 4rem;
}
</style>

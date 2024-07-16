<template>
  <main>
    <h1>This is a single card</h1>
    <h3>{{ pokemon.name }}</h3>
    <!-- <img :src="pokemon.imageUrl" alt="Pokemon image" /> -->
  </main>
</template>
<script>
export default {
  props: {
    pokemon: Object,
  },
  data() {
    return {
      // pokemonName: "",
      // pokemonColor: "",
    };
  },
};
</script>
<style scoped>
main {
  background-color: rgb(98, 227, 51);
  width: 100%;
  height: 100%;
}

h3 {
  text-align: center;
  padding-top: 30px;
}
</style>

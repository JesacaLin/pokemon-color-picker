<template>
  <main>
    <h3>{{ pokemonName }}</h3>
    <h5>Pokemon's color: {{ pokemonColor }}</h5>
  </main>
</template>
<script>
export default {
  data() {
    return {
      pokemonName: "Card Title",
      pokemonColor: "purple",
    };
  },
};
</script>
<style scoped>
main {
  background-color: white;
  width: 50%;
}

h3 {
  text-align: center;
  padding-top: 30px;
}
</style>

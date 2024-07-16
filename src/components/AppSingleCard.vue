<template>
  <main class="card">
    <img :src="imageUrlGenerator(pokemon.id)" alt="Pokemon image" />
    <span>{{ pokemon.name }}</span>
  </main>
</template>
<script>
export default {
  props: {
    pokemon: Object,
  },
  methods: {
    imageUrlGenerator(id) {
      return `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${id}.png`;
    },
  },
  data() {
    return {};
  },
};
</script>
<style scoped>
.card {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  padding: 10px;
  background-color: lavender;
  border-radius: 20px;
  border: solid 0.25rem black;
  box-shadow: 1rem 1rem 0 -0.25rem #ceeef8, 1rem 1rem 0 0 white;
  transition: box-shadow;
  span {
    padding-right: 20px;
  }
  width: 100%;
}

.card:hover {
  box-shadow: 0.5rem 0.5rem 0 -0.25rem #ceeef8, 0.5rem 0.5rem 0 0 black;
}
</style>

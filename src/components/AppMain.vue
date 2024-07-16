<template>
  <main>
    <section class="container">
      <header>
        <span class="moustache">{}</span>
        <img v-bind:src="pokeHero" />
        <span class="moustache">{}</span>
      </header>

      <h2>What is your favorite color?</h2>
      <input type="text" placeholder="Enter a color" v-model.lazy="pokeColor" />

      <div class="checked-box-section">
        <input type="checkbox" name="dice" id="dice" v-model="dice" />
        <span>Row the dice</span>
      </div>
      <h5 v-if="dice">You rolled {{ getRandomColorNumber }}</h5>
      <button @click.prevent="fetchPokemonData">Show me my Pokemon!!</button>
    </section>
    <section class="cardContainer">
      <AppCards :cardsArray="pokemonData" />
    </section>
  </main>
</template>

<script>
import AppCards from "./AppCards.vue";

export default {
  components: {
    AppCards,
  },
  computed: {
    getRandomColorNumber() {
      return Math.floor(Math.random() * 10) + 1;
    },
  },
  methods: {
    async fetchPokemonData() {
      const apiUrl = `https://pokeapi.co/api/v2/pokemon-color/${this.pokeColor}`;
      try {
        const response = await fetch(apiUrl);
        if (!response.ok) throw new Error("Failed to fetch");
        const data = await response.json();
        this.pokemonData = data;
        console.log(this.pokemonData);
      } catch (error) {
        console.log(error);
      }
    },
  },

  data() {
    return {
      pokeColor: "",
      pokemonData: null,
      dice: false,
      pokeHero:
        "https://64.media.tumblr.com/50b0cce4c263e8c11ca8ee6a1961dde7/tumblr_mph6fxYXO91so85hio1_500.jpg",
    };
  },
};
</script>
<style scoped>
main {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: auto;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

input {
  width: 20rem;
  height: 3rem;
  border-radius: 10px;
}

#dice {
  width: 2rem;
}

button {
  width: 15rem;
  height: 3rem;
  border-radius: 30px;
}

img {
  width: 90%;
}

.moustache {
  font-size: 60px;
}

header {
  display: flex;
  align-items: center;
}

.checked-box-section {
  display: flex;
  align-items: center;
  gap: 1rem;
}
</style>

// pokeHero: //
"https://i.pinimg.com/originals/e8/e7/b7/e8e7b71dc7349968cfa88364194d97e9.jpg",

<script>
import AppHeader from "./components/AppHeader.vue";
import AppCards from "./components/AppCards.vue";
import AppMain from "./components/AppMain.vue";

export default {
  components: {
    AppHeader,
    AppCards,
    AppMain,
  },

  methods: {},

  mounted() {},

  computed: {},

  data() {
    return {};
  },
};
</script>

<template>
  <div class="grid-container">
    <header>
      <AppHeader />
    </header>
    <main>
      <AppMain />
    </main>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
}
/* .grid-container {
  display: grid;
  grid-column: repeat(2, 1fr);
  grid-template-rows: 1fr 8fr;
  grid-template-areas:
    "header header"
    "main cardsArea";
}

header {
  grid-area: header;
}

main {
  grid-area: main;
}

section {
  grid-area: cardsArea;
} */
</style>

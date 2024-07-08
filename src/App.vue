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

  methods: {
    updateCurrentDate() {
      this.currentDate = new Date();
    },
  },

  mounted() {
    this.updateCurrentDate();
    setInterval(() => this.updateCurrentDate(), 1000);
  },

  computed: {
    calculateAverage() {
      if (this.scores.length === 0) {
        return 0;
      } else {
        let total = this.scores.reduce((a, b) => a + b, 0);
        return total / this.scores.length;
      }
    },
  },

  data() {
    return {
      firstName: "jae",
      lastName: "Brown",
      scores: [90, 85, 80],
      gradeLevel: 4,
      avatarURL: "https://source.boringavatars.com/bauhaus/80/jaeb",
      currentDate: new Date(),
    };
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
    <section>
      <AppCards />
    </section>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
}
.grid-container {
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
}
</style>

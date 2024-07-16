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
  box-sizing: border-box;
}
</style>

<template>
  <main>
    <h1>This is a cards container</h1>

    <section>
      <app-single-card />
    </section>
  </main>
</template>
<script>
import AppSingleCard from "./AppSingleCard.vue";
export default {
  components: {
    AppSingleCard,
  },
};
</script>

<style scoped>
h1 {
  text-align: center;
  padding-top: 30px;
}
main {
  background-color: lightcoral;
  width: 100%;
  height: 100%;
}
</style>

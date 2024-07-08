<template>
  <div
    class="student-info"
    v-bind:class="{ elementary: gradeLevel <= 5, middle: gradeLevel > 5 }"
  >
    <h1>Rae Brown</h1>
  </div>
</template>

<script>
export default {
  props: {
    gradeLevel: Number,
  },
};
</script>

<style scoped>
.student-info {
  background-color: lightblue;
  color: #292949;
  margin-bottom: 1rem;
  padding: 1rem 1rem;
  width: 300px;
}

.elementary {
  background-color: lightcoral;
}

.middle {
  background-color: lightgreen;
}

h1 {
  font-size: 1.5rem;
  margin: 0;
}
</style>

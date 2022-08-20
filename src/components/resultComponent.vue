<template>
  <div>
    <div class="result">
      <div class="title">{{ results[resultIndex].title }}</div>
      <div class="desc">{{ results[resultIndex].desc }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "resultComponent",
  props: {
    correctAnswer: Number,
    results: Object,
  },
  computed: {
    resultIndex() {
      let index = 0;
      this.results.forEach((result, i) => {
        if (result.min >= this.correctAnswer && result.max <= this.correctAnswer) {
          index = i;
        }
      });
      return index;
    },
  },
};
</script>

<style></style>

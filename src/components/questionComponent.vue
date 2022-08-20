<template>
  <div>
    <div class="questions-ctr">
      <barComponentVue :barInformation="barInformation"></barComponentVue>
      <div
        v-show="questionAnswerd === index"
        v-for="(question, index) in questions"
        :key="index"
        class="single-question"
      >
        <div class="question">
          {{ question.q }}
        </div>

        <div v-for="(answer, index) in question.answers" :key="index" class="answers">
          <div @click.prevent="answerd(answer.is_correct)" class="answer">
            {{ answer.text }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import barComponentVue from "./barComponent.vue";
export default {
  name: "questionComponent",
  components: {
    barComponentVue,
  },
  props: {
    questions: Object,
    questionAnswerd: Number,
  },
  data() {
    return {
      barInformation: {
        answerdQuestion: 0,
        totalQuestion: this.questions.length,
      },
    };
  },
  emits: ["questionAnswerd"],
  methods: {
    answerd(is_correct) {
      this.barInformation.answerdQuestion++;
      this.$emit("questionAnswerd", is_correct);
    },
  },
};
</script>

<style></style>

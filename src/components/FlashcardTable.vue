<template>
  <div>
    <h1>Star Wars Trivia</h1>

    <div class="filter-btn-container">
      <button class="filter-btns" value="easy" @click="updateDifficulty">
        Easy
      </button>
      <button class="filter-btns" value="medium" @click="updateDifficulty">
        Medium
      </button>
      <button class="filter-btns" value="hard" @click="updateDifficulty">
        Hard
      </button>
      <button class="filter-btns" value="all" @click="updateDifficulty">
        Show All
      </button>
    </div>
    <p>Hover over the Cards to reveal the answer</p>
    <div class="all-cards">
      <div v-for="question in questions" :key="question.id">
        <flash-card
          :card="question"
          @show-answer="revealAnswer"
          :difficulty="difficulty"
        />
      </div>
    </div>
  </div>
</template>

<script>
import questionList from "../trivia";
import FlashCard from "./FlashCard.vue";

export default {
  components: { FlashCard },
  methods: {
    revealAnswer(question) {
      question.answerShown = !question.answerShown;
      console.log(question);
    },
    updateDifficulty(e) {
      switch (e.target.value) {
        case "easy":
          this.difficulty = "easy";
          break;
        case "medium":
          this.difficulty = "medium";
          break;
        case "hard":
          this.difficulty = "hard";
          break;
        default:
          this.difficulty = "";
      }
    },
  },
  data() {
    return {
      questions: [...questionList],
      difficulty: "",
    };
  },
};
</script>

<style>
.all-cards {
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-flow: wrap;
}

.indiv-card {
  margin: 4px;
}

.filter-btns {
  height: 70px;
  width: 155px;
  margin: 4px;
  border: 5px solid black;
}

.filter-btn-container {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
</style>

<template>
  <!-- Front of Card -->
  <div v-if="(difficulty == card.difficulty || !difficulty)">
    <div class="flip-card">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <div class="card-bgd" :class="{ showAnswerBgd: card.answerShown }">
            <div>
              <h3 v-if="!card.answerShown" class="gold-text spacing">
                {{ card.question }}
              </h3>
              <h3 v-else>{{ card.answer }}</h3>
            </div>
          </div>
        </div>
        <div class="flip-card-back">
          <h3>{{ card.answer }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["card", "difficulty"],
  data() {
    return {};
  },
  methods: {
    showAnswer() {
      this.$emit("show-answer", this.card);
    },
  },
};
</script>

<style>
.card-bgd {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  background-color: red;
  margin: 4px;
  width: 250px;
  height: 250px;
}

/* .showAnswerBgd {
  background-color: rgba(0, 0, 255, 0.139);
} */

.gold-text {
  color: yellow;
}

.spacing {
  padding: 15px;
}

.btn-size {
  width: 170px;
  height: 50px;
}

.visible {
  visibility: hidden;
}

.flip-card {
  background-color: transparent;
  width: 250px;
  height: 250px;
  border: 1px solid #f1f1f1;
}

/* This container is needed to position the front and back side */
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

/* Do an horizontal flip when you move the mouse over the flip box container */
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

/* Position the front and back side */
.flip-card-front,
.flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden; /* Safari */
  backface-visibility: hidden;
}

/* Style the front side (fallback if image is missing) */
.flip-card-front {
  /* background-color: #bbb; */
  color: black;
}

/* Style the back side */
.flip-card-back {
  background-color: rgba(0, 0, 255, 0.29);
  color: white;
  transform: rotateY(180deg);
}
</style>

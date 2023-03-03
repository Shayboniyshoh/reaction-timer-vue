<template>
  <h1>Reaction Timer App</h1>
  <button @click="startGame" :disabled="isPlaying">Start</button>
  <BlockItem v-if="isPlaying" :delay="delay" @end="endGame" />
  <ResultsItem v-if="showResult" :score="score" />
</template>

<script>

import BlockItem from "./components/BlockItem.vue";
import ResultsItem from "./components/ResultsItem.vue";

export default {
  name: 'App',
  components: { BlockItem, ResultsItem },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false
    }
  },
  methods: {
    startGame() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTime) {
      this.isPlaying = false;
      this.score = reactionTime;
      this.showResult = true;
    }
  }
}
</script>

<style>
body {
  background: #555;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #333;
  margin-top: 60px;
}

h1,
p {
  color: #fff;
}
</style>

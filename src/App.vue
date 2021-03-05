<template>
  <div id="app">
    <FlashCardTable />
  </div>
</template>

<script>
import FlashCardTable from "./components/FlashcardTable";

export default {
  components: {
    FlashCardTable,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

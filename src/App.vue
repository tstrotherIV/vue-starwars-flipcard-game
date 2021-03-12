<template>
  <div id="app" >
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
body {
  background-image: url('https://www.denofgeek.com/wp-content/uploads/2020/07/star-wars-squadrons-zoom-background.jpg?fit=1920%2C1080');
  object-fit: fill;
  background-attachment: fixed;
  background-position: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

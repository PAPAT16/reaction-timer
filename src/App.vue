
<template>
  <h1>Ninja Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <block v-if="isPlaying" :delay="delay" @end="endGame" />
  <!-- <p v-if="showResults">Reaction time: {{ score}} ms</p> -->
  <result v-if="showResults" :score="score"/>
</template>

<script>
import block from "./components/block.vue";
import result from "./components/result.vue";

export default {
  name: "App",
  components: { block, result},
  data() {
    return {
      isPlaying: false,
      delay: null,
      score:null,
      showResults:false
    };
  },

  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      // console.log(this.delay);
    },
    endGame(reactionTime){
      this.score =reactionTime
      this.isPlaying = false
      this.showResults = true
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
  font-family: cursive
}
body{
  background: #50ccad;
}
button{
  /* background: #349b81; */
  padding: 10px;
  font-size: 20px;
  border: none;
  color: #50ccad;
  border-radius: 20px;
  text-align: center;
  width: 150px;
}
button[disabled]{
  background-color: #13493c;
}
</style>

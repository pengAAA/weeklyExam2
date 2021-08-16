<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <major-clock></major-clock>
    <control-buttons></control-buttons>
    <split-times></split-times>
  </div>
</template>

<script>

// import HelloWorld from "./components/HelloWorld.vue";
import MajorClock from "./components/MajorClock.vue";
import ControlButtons from './components/ControlButtons.vue';
import SplitTimes from './components/SplitTimes.vue';

export default {
  name: "App",
  components: {
    // HelloWorld,
    MajorClock,
    ControlButtons,
    SplitTimes
  },
  methods: {
    change (value) {
      this.val = value
    }
  }
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

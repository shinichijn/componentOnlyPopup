<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    <div>
      <h1>This is a demo for a single component pop up window <br />
      to serve such as printing or escape parent structure. </h1>
      <input v-model="msg" style="width: 25%" />
      <input type="checkbox" v-model="open" /> Check me!
    </div>
    <WindowPortal v-model="open">
      <HelloWorld :msg="msg" />
    </WindowPortal>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import WindowPortal from './components/WindowPortal';

export default {
  name: "App",
  components: {
    HelloWorld,
    WindowPortal
  },
  data() {
    return {
      msg: 'Hello from another window!',
      open: false,
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

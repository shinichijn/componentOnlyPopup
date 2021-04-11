<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    <div>
      This input is used in the header of the opened window. <br />
      Try updating it while the window is open! 
      <br />
      <input v-model="msg" style="width: 25%" />
      <br />
      <input type="checkbox" v-model="open" /> Check me to open a portal!
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

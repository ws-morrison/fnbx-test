<template>
  <div id="app">
    <the-item/>
  </div>
</template>

<script>
import TheItem from "./components/TheItem";
export default {
  name: "App",
  components: {
    TheItem
  }
};
</script>

<style lang="scss">
body {
  background-image: url("../src/assets/Pattern.jpg");
  font-family: "Trebuchet MS", Arial, sans-serif;
}
</style>

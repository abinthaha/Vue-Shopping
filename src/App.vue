<template>
  <div id="app">
    <app-landing></app-landing>
  </div>
</template>

<script>
import Landing from "./components/LandingComponent.vue";

export default {
  name: "app",
  components: {
    'app-landing': Landing
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
}

html, body {
  min-height: 100%;
  margin: 0;
  padding: 0;
  height: 100%;
}
</style>

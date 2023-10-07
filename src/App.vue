<template>
  <div id="app">
    <NavBar />
    <div class="main-content">
      <router-view />
    </div>
  </div>
</template>

<script>
import NavBar from "./components/NavBar.vue";

export default {
  name: "App",
  components: {
    NavBar,
  },
};
</script>

<style>
:root {
  --navbar-width: 250px;
}

html,
body {
  height: 100%;
}

#app {
  font-family: "Gloria Hallelujah", cursive;
  font-family: "Varela Round", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  display: flex;
}

.main-content {
  flex-grow: 1;
  padding: 20px;
  margin-left: var(--navbar-width, 300px);
}
</style>

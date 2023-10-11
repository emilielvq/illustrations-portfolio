<template>
  <div class="container">
    <nav>
      <ul id="navbar-menu">
        <li>
          <router-link to="/"
            ><img
              id="logo"
              src="@/assets/logo_prov.png"
              alt="Logo Emilie Levaique"
          /></router-link>
        </li>
        <li><router-link to="gallery">Gallery</router-link></li>
        <li><router-link to="process">Process</router-link></li>
        <li><router-link to="about">About</router-link></li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
.container {
  position: fixed;
  width: var(--navbar-width, 300px);
  display: flex;
  flex-direction: column;
  align-items: left;
  height: 100%;
  top: 0;
  left: 0;
  height: 100vh;
  z-index: 3;
}

#logo {
  height: auto;
  width: auto;
  max-height: 80%;
  max-width: 80%;
}

nav {
  background-color: #333;
  color: #fff;
  height: 100%;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  font-size: 1.3rem;
  transition: color 0.3s ease;
}

nav a.router-link-exact-active {
  color: #42b983;
}

#navbar-menu {
  list-style: none;
  padding: 0;
  margin-top: 40px;
  margin-left: 30px;
}

#navbar-menu li {
  margin-bottom: 20px;
}

#navbar-menu a {
  text-decoration: none;
  color: #fff;
  transition: color 0.3s ease;
}

#navbar-menu a:hover {
  color: #00bcd4;
}
</style>

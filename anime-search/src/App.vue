<template>
  <div id="app">
    <div id="menu">
      <div id="brand">
        <router-link to="/">
          <img src="../public/animeLogo.png" />
        </router-link>
      </div>
      <div id="side">
        <router-link to="/favorite">Your Favorite Anime</router-link>
        <router-link to="/recommendation">Recommendations</router-link>
      </div>
    </div>
    <router-view />

    <div class="github-container">
      <ul class="social-links">
        <li>
          <a
            href="https://github.com/mgordillo11/CS260-Creative-Project-3"
            target="blank"
            ><i class="fab fa-github"></i
          ></a>
        </li>
      </ul>
    </div>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: lightgoldenrodyellow;
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: #b84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

.github-container {
  display: flex;
  justify-content: center;
  font-size: 100px;
}

.fab {
  color: black;
}

.github-container li {
  list-style: none;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: space-evenly;
}
</style>

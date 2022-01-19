<template>
  <div class="navbar">
    <router-link to="/">Home</router-link> |
    <router-link to="/profile">Profile</router-link>
  </div>
  <router-view />
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Lato:wght@100;400;700&display=swap");

* {
  margin: 0;
  padding: 0;
}

body {
  background: #1e2836;
  box-sizing: border-box;
  padding: 15px 25px;
  font-size: 24px;
}

#app {
  font-family: "Lato", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #f0f0f0;
}

.navbar {
  text-align: center;
  margin: 0 auto 15px;
  width: 100%;
  box-sizing: border-box;
  font-size: 0.8em;
}

.navbar a {
  font-weight: bold;
  color: #f0f0f0;
  margin: 0 10px;
}

.navbar a.router-link-exact-active {
  color: #b1b942;
}

button {
  font-family: inherit;
  font-weight: bold;
  font-size: 1em;
  margin-top: 15px;
  padding: 10px 15px;
  background: #b1b942;
  border-radius: 5px;
  outline: none;
  color: #1e2836;
  border: 2px solid #cdcdcd;
  box-shadow: 3px 3px 10px #000;
  appearance: none;
}

button:hover {
  box-shadow: none;
}

button:active {
  color: #cdcdcd;
  background: #1e2836;
}
</style>

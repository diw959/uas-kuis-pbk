<template>
  <div id="app">
    <header>
      <nav>
        <ul>
          <li><router-link to="/">Cuaca</router-link></li>
          <li><router-link to="/location">Lokasi</router-link></li>
          <li><router-link to="/stopwatch">Stopwatch</router-link></li>
          <li><router-link to="/tictactoe">Game</router-link></li>
          <li><router-link to="/photo">Photo</router-link></li>
        </ul>
      </nav>
    </header>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>
#app {
  text-align: center;
}

header {
  background: linear-gradient(to right, #000000, #333333);
  padding: 20px;
  color: #fff;
  font-family: Arial, sans-serif;
  position: relative;
  overflow: hidden;
}

header::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url(https://img.freepik.com/premium-photo/chatgpt-inscription-cyber-background-ai-generation_235573-2503.jpg);
  background-size: cover;
  background-position: center;
  z-index: -1;
  opacity: 0.5;
}

body{
  background-image: url(https://cdn.wallpapersafari.com/91/12/BNZxzM.gif);
}
nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

nav li {
  display: inline-block;
  margin-right: 10px;
}

nav a {
  color: #15fab5;
  text-decoration: none;
  padding: 5px 10px;
  border-radius: 4px;
  transition: background-color 0.3s;
}

nav a:hover {
  background-color: rgb(173, 156, 156);
  text-decoration: none;
  transform: scale(1.1);
}
</style>

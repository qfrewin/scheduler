<template>
  <div id="app">
    <div class="header-container">
      <img src="/images/logo_light.svg" width="300px">
      <div class="links">
        <router-link to="/">
          <button>Home</button>
        </router-link>
        <router-link to="/assignments">
          <button>Asignments</button>
        </router-link>
      </div>
    </div>



    <div class="content">
      <router-view/>
    </div>

    <div class="footer-container">
      <div class="links">
        <a href="https://github.com/qfrewin/creativeProject3"><button>GitHub</button></a>
      </div>
    </div>
  </div>
</template>

<style>
* {
  margin: 0px;
  padding: 0px;
  border: 0px;
  box-sizing: border-box;
}

.content {
  display: flex;
  justify-content: start;
  align-items: flex-start;
  width: 100%;
  height: auto;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.header-container {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  height: auto;
  width: 100%;
  background-color: #0abab4;
  padding: 10px 50px;
}

.links {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

.links
button {
  padding: 20px;
  background-color: transparent;
  font-size: 18px;
  font-weight: bold;
}
.header-container
button {
  color: #737373;
}
.footer-container
button {
  color: #daf5f4;
}
.header-container
button:hover {
  background-color: #daf5f4;
}
.footer-container
button:hover {
  background-color: #0abab4;
}

.footer-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100px;
  width: 100%;
  background-color: #356e6c;
  padding: 10px 50px;
}
</style>

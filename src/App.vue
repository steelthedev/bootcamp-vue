<template>

  <router-view/>
</template>

<script>
export default {
  name:'App'
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Mukta:wght@200;300;500&family=PT+Sans:ital,wght@0,400;1,700&family=Roboto+Mono:wght@200;300&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Michroma&display=swap');


body{
  font-family:'Open Sans', sans-serif;
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
</style>

<template>
  <div id="app">
    <div id="nav">
      <img src="./assets/marvel-background3.jpg">
    </div>
    <List/>
  </div>
</template>

<script>
import List from './components/List'

export default {
  name: 'App',
  components: {
    List
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #f1f2f0;
}
#nav{
  background-color: #b93b3f;
  height: 90px;
}
img{
  width: 15%;
  border: 2px solid white;
  margin-top: 5px;
}
</style>

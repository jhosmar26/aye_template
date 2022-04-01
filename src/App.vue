<template>
  <div id="app">
    <PageInProgress/>
  </div>
</template>

<script>
import PageInProgress from "./pages/pageInProgress.vue"
export default {
  name: 'App',
  components: {
    PageInProgress
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Ubuntu:wght@500&display=swap');

body{
  margin: 0;
}

#app{
  background: linear-gradient(75deg, rgba(88,239,236,1) 10%, rgba(9,166,243,1) 130%);
  min-height: 100vh;
  font-family: 'Ubuntu', sans-serif;
}
</style>

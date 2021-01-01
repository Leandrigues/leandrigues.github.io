<template>
  <div id="app">
    <div id="app-container">
      <Name/>
      <About/>
    </div>
  </div>
</template>

<script>
import Name from './components/Name.vue'
import About from './components/About.vue'


export default {
  name: 'App',
  components: {
    Name,
    About,
  }
}
</script>

<style>
  body, html {
    margin: 0;
    height: 100%;
    background-color: rgb(249, 251, 232); 
  }

  #app {
    height: 100%;
    width: 100%;
    background-color: rgb(249, 251, 232); 
    display: flex;
    justify-content: center;
  }

  #app-container {
    width: 40%;
  }
  @media only screen and (max-width: 1050px) {
    #app-container {
      width: 100%;
    }
  }
</style>

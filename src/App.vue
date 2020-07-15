<template>
  <div id="app" class="background">
    <div class="container">
      <h1>CONTADOR DE CLICKS</h1>
      <Contador/>
    </div>
  </div>
</template>

<script>
import Contador from './components/Contador.vue'

export default {
  name: 'App',
  components: {
    Contador
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Knewave&display=swap');
body {
  margin: 0 !important;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.background {
  position: absolute;
  height: 100%;
  width: 100%;
  overflow: auto;
  background: linear-gradient(to bottom, #374785, #24305e) fixed;
}
.container {
  background-color: #24305e;
  border-radius: 1px;
  padding: 25px;
  margin: auto;
  backdrop-filter: blur(5px);
  max-width: 340px;
  height: fit-content;
  position: absolute;
  top: 0; left: 0; bottom: 25%; right: 0;
  color: #F8E9A1;
  box-shadow: -8px 8px 0px -4px rgba(0, 0, 0, 0.623);
}
h1 {
  color: #ff6161;
  text-shadow: 1pt 1pt #d2e4eef1;
  font-weight: 500;
  font-size: 50px;
  margin: 0;
  font-family: 'Knewave', cursive;
}
</style>

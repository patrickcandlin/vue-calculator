<template>
    <Calculator />
</template>

<script>
import Calculator from './components/Calculator.vue'

export default {
  components: {
    Calculator
  }
}
</script>

<style>
body {
  background: #00B3E6;
  box-sizing: border-box;
  margin: 0;
  padding: 20px;
  width: 100%;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>

<template>
<the-main></the-main>
</template>

<script>
import TheMain from './components/Layout/TheMain.vue'

export default {
  name: 'App',
  components: {
    TheMain
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
body{
 background: #F8F8F8 0% 0% no-repeat padding-box;
 opacity: 1;
}
</style>

<template>
  <div id="app">
    <Email/>
  </div>
</template>

<script>
import Email from './components/email.vue'

export default {
  name: 'App',
  components: {
    Email
  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app{
  margin:50px
}
</style>

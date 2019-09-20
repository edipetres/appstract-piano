<template>
      <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  }
}
</script>

<style lang="scss">

@import './components/theme.scss';

body {
  margin: 0;
}

body, html {
  background-color: $grey-background-color;
}

</style>

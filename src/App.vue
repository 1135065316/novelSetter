<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  methods: {
    
  }
}
</script>

<style lang="scss">
  * {
    margin: 0;
    padding: 0;
  }
  html,body,#app{height:100%;}
  @font-face
  {
  font-family: hanzi01;
  src: url('./assets/fonts/hanzi01.ttf');
  }
</style>

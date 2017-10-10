<template>
  <div id="app">
    <img style="width:30%" src="http://68.media.tumblr.com/0111b2d5803658020903787c1d25b548/tumblr_mij4k99VVZ1rp1r7to1_r1_1280.gif">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: Lobster;
  /*-webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;*/
  text-align: center;
  /*color: #2c3e50;
  margin-top: 60px;*/
}
</style>

<template>
  <div id="app">
    <div class="ec-container">
      <img alt="Spotify Logo" src="@/assets/spotify-logo.png">
    </div>
  </div>
</template>


<script>
export default {
  name: 'HeaderLayout',
}
</script>

<style lang="scss" scoped>

.ec-container {
  width: 100%;
  height: 100px;
  line-height: 100px;
  vertical-align: middle;
  background-color: #2e3a46;
  img {
    height: 50px;
  }
}
</style>
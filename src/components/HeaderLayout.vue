<template>
  <div id="app">
    <div class="container">
      <img alt="Spotify Logo" src="@/assets/spotify-logo.png">
      {{message}}
    </div>

  </div>
</template>

<script>
export default {
  name: 'HeaderLayout',
  props: {
    message: String
  } //input che riceve dall'esterno
}
</script>

<style lang="scss">

.container {
  height: 100px;
  background-color: #2e3a46;
  img {
    height: 50px;
  }
}


</style>
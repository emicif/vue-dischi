<template>
  <div id="app">
    <HeaderLayout :message="'Spotify'"/>
    <MusicList :url="apiUrl"/>
  </div>
</template>

<script>
 
import HeaderLayout from '@/components/HeaderLayout.vue'
import MusicList from '@/components/MusicList.vue'



export default {
  name: 'App',
  components: {
    HeaderLayout,
    MusicList,
  },
  data () {
    return {
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music'
    }
  }
}
</script>

<style lang="scss">

@import '@/style/general';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>

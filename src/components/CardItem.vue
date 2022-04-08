<template>
  <div>
    <h2>
      <img :src="card.poster" :alt="card.title" />
      <p> {{card.author}} </p>
      <p> {{card.year}} </p>

    </h2>
  </div>
</template>

<script>

/*
    data:
        response: Array(10)
        0:
        author: "Bon Jovi"
        genre: "Rock"
        poster: "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
        title: "New Jersey"
        year: "1988"
    */

export default {
    name: 'CardItem',
    props: {
      card: Object
    }
}
</script>

<style lang="scss" scoped>

</style>
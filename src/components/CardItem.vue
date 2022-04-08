<template>
  <div class="container-fluid">
    <div class="ec-card">
        <img :src="card.poster" :alt="card.title" />
        <h3>{{card.title}}</h3>
        <p> {{card.author}} </p>
        <p> {{card.year}} </p>
    </div>
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



.ec-card {
  margin-top: 10px;
  border: 1px solid black;
  background-color: #2e3a46;
  height: 400px;
  width: 200px;
 
  img {
  height: 200px;
  padding: 20px;
  }
  h3 {
    color: white;
    text-transform: uppercase;
  }
  p {
    color: grey;
  }
}




</style>
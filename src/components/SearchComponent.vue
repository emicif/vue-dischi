<template>
  <div>
      <select @change = "showGenere($event)">
        <option value="">All</option>  
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
  </div>
</template>



<script>
export default {
    name: 'SearchComponent',
    data () {
        return {
           selectedGenere: '', 
        }
    },
    methods: {
        showGenere(event){
            console.log('ciao', event.target.value);
            this.selectedGenere = event.target.value;
            this.$emit('search', this.selectedGenere)
        }
    }
}
</script>

<style scoped>

</style>
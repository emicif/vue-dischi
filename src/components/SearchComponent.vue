<template>
  <div>
      <select @change = "showGenere($event)">
        <option value="Rock">Rock</option>
        <option value="Rock">Rock</option>
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
            this.$emit('search', this.selectedGenere)
        }
    }

}
</script>

<style>

</style>
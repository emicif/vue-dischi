<template>
<div>
    <div class="selettore">
        <select @change = "showGenere($event)">
            <option value="">Seleziona un genere musicale</option>  
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
        
    </div>
  
</div>
   
</template>



<script>
export default {
    name: 'SearchComponent',
    data () {
        return {
           selectedGenere: '', 
           selectedAuthor: '',
        }
    },
    methods: {
        showGenere(event){
            console.log('ciao', event.target.value);
            this.selectedGenere = event.target.value;
            this.$emit('search', this.selectedGenere)
        },
    }

}
</script>

<style scoped>
    .selettore {
        display: flex;
        justify-content: center;
        padding: 30px;
    }
    select {
        background-color: #2e3a46;
        color: white;
        padding: 15px 5px;
        border-radius: 10px;
        cursor: pointer;
        font-size: 20px;
    }
    
</style>
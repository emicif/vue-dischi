<template>
<div>
    <div class="selettore">
        <select @change = "showAuthor($event)">
            <option value="">Seleziona un autore</option>  
            <option value="Bon Jovi">Bon Jovi</option>
            <option value="Queen">Queen</option>
            <option value="Sting">Sting</option>
            <option value="Steve Gadd Band">Steve Gadd Band</option>
            <option value="Iron Maiden">Iron Maiden</option>
        </select>
    </div>
  
</div>
   
</template>



<script>
export default {
    name: 'SearchComponent',
    data () {
        return {
           selectedAuthor: '',
        }
    },
    methods: {
        showAuthor(event){
            console.log('ciao autore', event.target.value);
            this.selectedAuthor = event.target.value;
            this.$emit('search', this.selectedAuthor)
        }
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
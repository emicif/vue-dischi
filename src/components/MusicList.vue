<template>
  <div class="ec-container ">
     <div class="container-card">
 <div class="cardMusic"
        v-if="cards.length > 0">
            <CardItem v-for="item in cards" :key="item.id" :card="item"/>
        </div>

        <div v-else>
            <LoadingComponent />
        </div>
     </div>
       
     
        
  </div>
</template>

<script>
//importo axios, l'item delle varie card e il componente da visualizzare con caricamento lento
import axios from 'axios';
import CardItem from '@/components/CardItem.vue'
import LoadingComponent from '@/components/LoadingComponent.vue'

export default {
    name: 'MusicList',
    data(){
        return {
            cards: []
        }
    },
    props: {
        url: String
    },
    components: {
        CardItem,
        LoadingComponent
    },
    mounted(){
        this.loadData();
    },
    methods:{
        loadData(){
            axios.get(this.url).then(
                (response)=>{
                  //console.log(response)
                   if (response.status === 200){
                    this.cards = response.data.response;
                    console.log(this.cards[0]);
                   }
                }   
            ).catch((error)=>{
                console.log(error);
            })
        }
    }
}
</script>

<style lang="scss" scoped>
.ec-container {
  height: 100vh;
  background-color: #1e2d3b;
}

.cardMusic {
    display: flex;
    flex-wrap: wrap; 
}

.container-card {
    width: 60%;
    margin: 0px auto;

}

.ec-card {
    width: calc(100% / 5);
    padding: 10px;
}


</style>
<template>
  <div class="ec-container">
    <div 
    v-if="cards.length > 0" 
    class="col-12 col-md-6 col-xl-3 d-flex">
        <CardItem v-for="item in cards" :key="item.id" :card="item"/>
    </div>
    <div v-else>
        <LoadingComponent />
    </div>
  </div>
</template>

<script>
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
  max-width: 100%;
  height: 100vh;
  background-color: #1e2d3b;
  display: flex;
  flex-wrap: wrap;

}


</style>
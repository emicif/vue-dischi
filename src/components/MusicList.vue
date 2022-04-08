<template>
  <div>
    <div class="col-12 col-md-6 col-xl-3">
        <CardItem :card="cards[0]"/>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import CardItem from '@/components/CardItem.vue'

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
        CardItem
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

<style>

</style>
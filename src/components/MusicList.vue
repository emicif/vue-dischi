<template>
  <div class="ec-container ">
     <div class="container-card">
        <SearchComponent @search="filterGenere"/>
        <SearchAuthor @search="filterAuthor"/>
        <div class="cardMusic"
                v-if="cards.length > 0">
                    <CardItem 
                    v-for="item in filterList" 
                    :key="item.id" 
                    :card="item"/>
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
import SearchComponent from '@/components/SearchComponent.vue'
import SearchAuthor from '@/components/SearchAuthor.vue'

export default {
    name: 'MusicList',
    data(){
        return {
            cards: [],
            searchGenere: '',
            searchAuthor: '',
        }
       
    },
    props: {
        url: String
    },
    components: {
        CardItem,
        LoadingComponent,
        SearchComponent,
        SearchAuthor
      },
    mounted(){
        this.loadData();
    },
    methods:{
        loadData(){
            axios.get(this.url).then(
                (response)=>{
                  console.log(response)
                   if (response.status === 200){
                    this.cards = response.data.response;
                    console.log(this.cards[0]);
                   }
                }   
            ).catch((error)=>{
                console.log(error);
            })
        },
        filterGenere(searchGenere){
            this.searchGenere = searchGenere;
            console.log('searchGenere', searchGenere)
           
        },
        filterAuthor(searchAuthor){
            this.searchAuthor = searchAuthor;
            console.log('searchAuthor', searchAuthor)
        },
    },
    computed: {
        filterList(){
            return this.cards.filter((item)=>item.genre.includes(this.searchGenere)
            &&
            item.author.includes(this.searchAuthor))
            
        },
    }
  
}
</script>

<style lang="scss" scoped>
.ec-container {
  height: 150vh;
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
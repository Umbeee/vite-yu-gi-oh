<script>
import CardsContainer from './components/CardsContainer.vue';
import CardsFilter from './components/CardsFilter.vue';

import { store } from './store';


export default {
  name: "App",
  data(){
    return {
      store
    }
  },
  components: {
    CardsContainer,
    CardsFilter
   },
   created() {
     this.callApi();
   },
   methods: {
     callApi(){
      if(store.valueArchetype !== ''){
        axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${encodeURIComponent(store.valueArchetype)}`)
        .then((res)=>{
          this.store.arrayCarte = res.data.data
        })
      }else{
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=896')
        .then((res)=>{
          this.store.arrayCarte = res.data.data
        })
      }
     }
   }
}

</script>

<template>
  <CardsFilter @emitArche="callApi()"/>
  <CardsContainer/>
</template>

<style lang="scss" scoped>

</style>

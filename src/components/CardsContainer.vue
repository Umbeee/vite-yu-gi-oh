<script>

import SingleCard from './SingleCard.vue';
import { store } from '../store';



export default{
    name: "CardsContainer",
    data(){
        return{
                store
            }
    },
    components: {
        SingleCard
       
    }
}
</script>

<template>
    <div class="bg-orange"> 
        <div class="container">
            
            <div v-for="(elem, index) in store.arrayCarte" :key="index"
            class="card">
            <SingleCard :SingleCardData="elem"/>
            </div>
            
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .bg-orange{
        background-color: orange;
        padding: 20px;

    }
    .container{
        width: 90%;
        margin: 0 auto;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        background-color: white;
        padding: 30px;

        div{
            width: 19%;
            background-color: orange;
            margin-top: 10px;
            margin-bottom: 10px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            border-radius: 5px;
            
                img{
                    display: block;
                    width: 100%;
                }
            
        }
        
        
    }
</style>
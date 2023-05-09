<script>
import { createHydrationRenderer } from 'vue';
import { store } from '../store';


export default {

    name: "CardsFilter",
    data(){
        return{
            store
        }
    },
    created (){
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((res)=>{
            console.log(res.data)
            store.arrayArchetypes = res.data
        })
    }

}

</script>

<template>

    <div class="header">
        <h1>Yu-Gi-Oh Api!</h1>
        <span>Cerca per archetype</span>
        <select name="filter" id="select-cards" v-model="store.valueArchetype"
        @change="$emit('emitArche')">
            <option :value="elem.archetype_name" v-for="(elem, index) in store.arrayArchetypes">{{ elem.archetype_name }}</option>
        </select>
    </div>

</template>

<style lang="scss" scoped>
    .header{
        padding: 20px;
        text-align: center;
        select{
                margin: 20px;
            } 
    }

</style>
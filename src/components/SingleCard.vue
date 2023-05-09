<script>

    export default{
        name: "SingleCard",
        props: ['SingleCardData']
    }
</script>

<template>
    
      
            <img :src="SingleCardData.card_images[0].image_url" alt=" SingleCardData.name ">
            <h3>{{ SingleCardData.name }}</h3>
            <h5>{{SingleCardData.archetype}}</h5>
      
    
</template>

<style lang="scss" scoped>
    
        img{
            display: block;
            width: 100%;
        }
        h3,h5{
            text-align: center;
        }
        h3{
            color: white;
            padding: 15px;
        }
        h5{
            padding-bottom: 30px;
        }
    
</style>
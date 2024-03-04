<script>
import { store } from "../store.js"

export default {
    
    name:"CardElement",

    props:{
        cards: Object,
    },
}
</script>

<template>
    
        <li >
            <img :src="cards.cards_image" alt="">
            {{ cards.name }}
        </li>
    

</template>

<style lang="scss">

</style>
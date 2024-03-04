<script>
import {store} from "../store.js";
import CardElement from "./CardElement.vue";

export default{
    name: "CardItem",

    components:{
        CardElement,
    },


    data() {
        return{
            store,
        }
    }
}


</script>

<template>
    <ul>
        <CardElement 
        v-for="cardElement in store.cards">
        </CardElement>
    </ul>

</template>

<style>

</style>



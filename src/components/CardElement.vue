<script>
import { store } from "../store.js"

export default {
    
    name:"CardElement",

    props:{
        card: Object,
    },
}
</script>

<template>
    
        <li id="item">
            <img :src="card.card_images[0].image_url_small" alt="">
            <h4>
                {{ card.name }}
            </h4>

            <small>{{ card.archetype }}</small>
        </li>
    

</template>

<style lang="scss">
@use "../styles/newstyle.scss" as *;
@use "../styles/variables.scss" as *;

#item{
    display: flex;
    flex-direction: column;
    gap: 25px;

    background-color: #CA9249;

    width: calc(100% / 5 - 25px / 5 * 4);

    text-align: center;
    text-transform: uppercase;

}

</style>
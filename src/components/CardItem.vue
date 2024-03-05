<script>
import { store } from "../store.js";
import axios from "axios";
import CardElement from "./CardElement.vue";
import AppPagination from "./AppPagination.vue";
import AppSelect from "./AppSelect.vue"

export default {
    name: "CardItem",

    components: {
        CardElement,
        AppPagination,
        AppSelect
    },


    data() {
        return {
            store,
        }
    },
    methods: {
        selectArch() {
            let urlCard = "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0";
            //se ho l'archetipo
            if (this.store.archtypeSelezionato != "0") {
                urlCard = urlCard + "&archetype=" + this.store.archtypeSelezionato
                
            }
            console.log(urlCard.store)


            axios.get(urlCard)
                .then(res => {
                    console.log(res.data.data)
                    this.store.cards = res.data.data;
                    
                    this.load = true;
                })


        }
    },
    created() {
        axios.get("https://db.ygoprodeck.com/api/v7/archetypes.php").then(res => {
            console.log(res.data)
            this.store.archetypes = res.data
        })
    }
}


</script>

<template>
    <nav>
        <img src="../../public/img/yu-gi-oh.png" alt="">
        <h1>YU-Gi-Oh Api</h1>
    </nav>
    <div class="container-fluid">

        <AppSelect @select="selectArch()"></AppSelect>

        <div>

        </div>

        <div class="container">
            <AppPagination></AppPagination>
            <ul>
                <CardElement v-for="cardId in store.cards" :card="cardId" >
                </CardElement>
            </ul>

        </div>
    </div>

</template>

<style lang="scss">
@use "../styles/newstyle.scss" as *;

nav {
    padding: 20px;
    display: flex;
    align-items: center;

    img {
        width: 100px;
    }

    h1 {
        color: black;
        font-size: 40px;
    }
}

.container-fluid {
    padding: 30px;
    background-color: #CA9249;
}

ul {
    list-style-type: none;
    display: flex;
    flex-wrap: wrap;

    gap: 25px;
}
</style>

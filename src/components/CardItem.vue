<script>
import {store} from "../store.js";
import CardElement from "./CardElement.vue";
import AppPagination from "./AppPagination.vue";

export default{
    name: "CardItem",

    components:{
        CardElement,
        AppPagination
    },


    data() {
        return{
            store,
        }
    }
}


</script>

<template>
    <nav>
        <img src="../../public/img/yu-gi-oh.png" alt="">
        <h1>YU-Gi-Oh Api</h1>
    </nav>
    <div class="container-fluid">

        <div>
            
        </div>

        <div class="container">
            <AppPagination></AppPagination>
            <ul>
                <CardElement 
                v-for="cardId in store.cards"  :card="cardId">
                </CardElement>
            </ul>
    
        </div>
    </div>

</template>

<style lang="scss">
@use "../styles/newstyle.scss" as *;

nav{
    padding: 20px;
    display: flex;
    align-items: center;

    img{
        width: 100px;
    }

    h1{
        color: black;
        font-size: 40px;
    }
}
.container-fluid{
    padding: 30px;
    background-color: #CA9249;
}

ul{
    list-style-type: none;
    display: flex;
    flex-wrap: wrap;

    gap: 25px;
}

</style>



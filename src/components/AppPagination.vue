<script>
import {store} from "../store.js"

export default {
    name:"AppPagination",

    data(){
        return{
            store,
        }
    }
}
</script>

<template>
    
    
        <div class="card-number">
            Numero di carte: {{ store.cards.length }}

        </div>

    

</template>

<style>
.card-number{
    max-width: 1000px;
    margin: 0 auto;

    padding: 20px;
    font-size: 30px;
    background-color: black;
    color: white;
    
}

</style>
<script>
import {store} from "../store.js"

export default {
    name: "AppSelect",

    data(){
        return{
            store,
        }
    }
}
</script>

<template>

    <select name="select-arch" id="" @change="$emit(`select`)" v-model="this.store.archtypeSelezionato">
    <option value="0">Select card:</option>
    <option :value="ArchElement.archetype_name" v-for="ArchElement in this.store.archetypes">{{ ArchElement.archetype_name }}</option>
    
    </select>


</template>

<style lang="scss">

select{
    background-color: white;
    color: black;
}


</style>
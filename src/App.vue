<script>
import axios from "axios";
import CardItem from "./components/CardItem.vue";
import AppLoad from "./components/AppLoad.vue"

import {store} from "./store.js"

export default{

  data(){
    return{
      load:false,
      store,
    }
  },
  created(){
    let urlCard="https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0";
    axios.get(urlCard)
    .then(res =>{
      console.log(res.data.data)
      this.store.cards = res.data.data;
      this.load= true;
    })
  },
  components:{
    CardItem,
    AppLoad
  }
}





</script>

<template>
  
  <AppLoad v-if="!load"></AppLoad>

  <CardItem></CardItem>


</template>

<style lang="scss">
@use "./styles/newstyle.scss" as *;








</style>
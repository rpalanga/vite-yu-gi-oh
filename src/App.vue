<script>
import axios from "axios";
import CardItem from "./components/CardItem.vue";

import {store} from "./store.js"

export default{

  data(){
    return{
      cards:[],
    }
  },
  created(){
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
    .then(res =>{
      console.log(res.data.data)
      this.store.data = res.data.data
    })
  },
  components:{
    CardItem,
  }
}





</script>

<template>
  <h1>ciao</h1>

  <CardItem></CardItem>


</template>

<style lang="scss">
@use "./styles/newstyle.scss" as *;

h1{
  color: red;
}






</style>
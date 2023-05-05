<script>
import Header from '../src/components/Header.vue';
import Main from '../src/components/Main.vue';
import {store} from "../data/store";
import axios from "axios";

export default{
  components:{
    Header,
    Main
  },
  data(){
    store
  },
  methods:{
    getApi(){
      axios.get(store.apiUrl)
      .then(result => {
        store.resultArray = result.data.data;
        store.resultArray = store.resultArray.slice(0, 100)
        console.log(store.resultArray);
      })
    }
  },
  mounted(){
    this.getApi();
  }
  
}
</script>

<template>

  <Header />

  <Main @newGetApi="getApi" />

</template>

<style lang="scss">
@use '../scss/main.scss'

</style>
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
        console.log(this.resultArray);
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

  <Main />

</template>

<style lang="scss">
@use '../scss/main.scss'

</style>
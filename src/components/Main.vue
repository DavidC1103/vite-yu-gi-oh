<script>
import Cards from '../components/partials/Cards.vue'
import {store} from '../../data/store';
export default{
    components:{
        Cards
    },
    data(){
    return{
      store,
    }
  },
    methods:{
        getCardType(){
            store.newType = store.resultArray
            this.$emit("newGetApi")
    }
  }

    
}
</script>

<template>
    <main class="my-5 text-center">
        <select v-model="cardType" @change="getCardType" class="form-select mb-5 w-25" aria-label="Default select example" aria-placeholder="Select a type">
          <option value="">All cards</option>
          <option
            v-for="cardType in store.listType"
            :value="cardType"
            :key="cardType">{{cardType}}</option>
        </select>

        <div class="result d-flex align-items-center">
            <span class="fs-5">Found {{ store.resultArray.length }} cards su {{ store.length }}</span>
        </div>

        <div class="dc-container">
            <Cards
            v-for="card in store.resultArray"
            :key="card.id"
            :img="card.card_images[0].image_url_small"
            :name="card.name"
            :species="card.archetype || card.type"
            />

        </div>


    </main>
</template>

<style lang="scss">
    main{
        margin: 0 auto;
        background-color: white;
        width: 1320px;
        padding: 20px;
        .result{
            margin: 0 auto;    
            width: 96.8%;
            height: 55px;
            background-color: #212529;
            color: white;
            padding-left: 15px;
        }
        .dc-container{
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
        }
    }

</style>
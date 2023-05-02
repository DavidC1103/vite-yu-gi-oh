<script>
import Cards from '../components/partials/Cards.vue'
import {store} from '../../data/store';
export default{
    components:{
        Cards
    },
    data(){
        return {
            store
        }
    }

    
}
</script>

<template>
    <main class="my-5 text-center">
        <div class="result d-flex align-items-center">
            <span class="fs-3">Found 39 cards</span>
        </div>
        <div class="dc-container">
            <Cards
            v-for="card in store.resultArray"
            :key="card.id"
            :img="card.card_images.image_url_small"
            :name="card.name"
            :species="card.archetype"
            />

        </div>


    </main>
</template>

<style lang="scss">
    main{
        margin: 0 auto;
        background-color: white;
        height: 1000px;
        width: 1320px;
        padding: 20px;
        .result{
            margin: 0 auto;    
            width: 95%;
            height: 55px;
            background-color: #212529;
            color: white;
            padding-left: 15px;
            .dc-container{
                display: flex;
                justify-content: center;
                flex-wrap: wrap;
            }
        }
    }

</style>
<script>
import {store} from '../../../data/store';
export default{
    name: 'Cards',
    props:{
        name: String,
        img: Object,
        species: String,
    },


    data(){
        store
    }
    
}
</script>

<template>

            <div class="dc-card">
                <img :src="img" alt="">
                <div class="text">
                    <h5>{{ name }}</h5>
                    <span>{{ species }}</span>
                </div>
            </div>

</template>

<style lang="scss">
 
    .dc-card{
        width: calc(100% / 5);
        padding: 0 20px;
        margin-bottom: 50px;
        img{
            width: 100%;
            object-fit: cover;
        }
        .text{
            background-color: #D48F38;
            padding-bottom: 20px;
            h5{
                color: white;
                padding-top: 15px;
                padding-bottom: 10px;
            }
        }
    }



</style>
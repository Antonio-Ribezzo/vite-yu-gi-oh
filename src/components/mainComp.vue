<script>
    import {store} from '../store.js'

    import cardItem from '../components/cardItem.vue'
    export default {
        name: 'mainComp',

        components:{
            cardItem
        },

        data(){
            return{
                store
            }
        }
    }
</script>

<template>
    <div id="mainContainer">
        <div class="container py-5">
            <!-- select -->
            <div class="my-2 col-3">
                <select class="form-select" aria-label="Default select example">
                    <option value="1">Alien</option>
                    <option value="2">Two</option>
                    <option value="3">Three</option>
                    <option value="4">Four</option>
                </select>
            </div>
            <!-- main container -->
            <main class="p-4 rounded">
                <!-- counter -->
                <div class="bg-secondary rounded p-3 text-center text-white">
                    <span>Found {{ store.arrayCards.length }} cards</span>
                </div>

                <!-- cards -->
                <div class="d-flex justify-content-between align-items-center flex-wrap mt-4">
                    <cardItem v-for="(el,index) in store.arrayCards" :key="index"
                    />
                </div>
            </main>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    #mainContainer{
        background: rgb(121,110,9);
        background: linear-gradient(90deg, rgba(121,110,9,1) 12%, rgba(121,52,9,1) 65%, rgba(228,46,12,1) 100%);
    }

    main{
        background-color: white;
    }
</style>
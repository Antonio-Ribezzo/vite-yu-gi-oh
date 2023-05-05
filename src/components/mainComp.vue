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
    <main>
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
            <!-- container  cards-->
            <div id="containerCards" class="p-4 rounded">
                <!-- counter -->
                <div id="counter" class="rounded p-3 text-center text-white">
                    <p class="m-0">
                        Found 
                            <span class="rounded-circle p-2 mx-2 bg-success">
                                {{ store.arrayCards.length }}
                            </span> 
                        cards
                    </p>
                </div>

                <!-- cards -->
                <div class="d-flex justify-content-between align-items-start flex-wrap mt-4">
                    <cardItem v-for="(el,index) in store.arrayCards" 
                    :key="index"
                    :arrayCards="el"
                    />
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
    main{
        background: rgb(121,110,9);
        background: linear-gradient(90deg, rgba(121,110,9,1) 12%, rgba(121,52,9,1) 65%, rgba(228,46,12,1) 100%);
    }

    #containerCards{
        background-color: rgba(0, 0, 0, 0.275);
    }

    #counter{
        background-color: orange;
        font-size: 20px;
    }
</style>
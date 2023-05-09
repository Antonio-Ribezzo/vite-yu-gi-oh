<script>
    import {store} from '../store.js'

    export default {
        name: 'selectComp',
        data(){
            return{
                store
            }
        }

    }
</script>

<template>
    <!-- select -->
    <div id="containerSelect">
        <div class="container pt-4 pb-2">
            <div class="col-3">
                <select class="form-select" @change="$emit('search')" v-model="store.nomeArchetype">
                    <option value="" selected>Choose an Archetype</option>
                    <option v-for="(el,i) in this.store.arrayArchetypes" :key="i" :value="el.archetype_name">{{ el.archetype_name }}</option>
                </select>
            </div>
        </div>
    </div>
</template>



<style lang="scss" scoped>
    #containerSelect{
        background: rgb(121,110,9);
        background: linear-gradient(90deg, rgba(121,110,9,1) 12%, rgba(121,52,9,1) 65%, rgba(228,46,12,1) 100%);
    }
</style>
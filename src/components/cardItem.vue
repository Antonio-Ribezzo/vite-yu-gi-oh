<script>
    export default {
        name: 'cardItem',
        props: ['arrayCards']
    }
</script>

<template>
    <div id="card" class="my-2 text-center px-2 py-4 rounded">
        <!-- immagine card -->
        <div>
            <img :src="arrayCards.card_images[0].image_url_small" :alt="'card-number-' + arrayCards.card_images[0].id">
        </div>
        <!-- nome della card -->
        <span class="d-block text-white text-uppercase mt-2">{{ arrayCards.name }}</span>
        <!-- nome archetype -->
        <span class="d-block mt-2">{{ arrayCards.archetype }}</span>
    </div>
</template>



<style lang="scss" scoped>
    #card{
        background-color: orange;
        width: calc((100% / 5) - 1rem);
        height: 25rem;
        div{
            img{
                width: 12rem;
            }
        }
    }
</style>
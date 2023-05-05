<script>
    import "@fontsource/alike-angular"
    export default {
        name: 'headerComp'
    }
</script>


<template>
    <header>
        <div class="container p-4 text-center position-relative">
            <!-- title -->
            <h1 class="text-white">Yu-Gi-Oh API</h1>
            <!-- logo centrale -->
            <div class="position-absolute">
                <img src="/img/logo-main.png" alt="logo-yu-gi-oh-principale">
            </div>
        </div>
    </header>
</template>


<style lang="scss" scoped>
    header{
        background: rgb(121,110,9);
        background: linear-gradient(90deg, rgba(121,110,9,1) 12%, rgba(121,52,9,1) 65%, rgba(228,46,12,1) 100%);
    }
    h1{
        font-family: "Alike Angular", sans-serif;
        font-size: 6rem;
    }
    img{
        height: 5em;
    }

    .position-absolute{
        bottom: -25%;
        left: 50%;
        transform: translate(-50%);
    }
</style>
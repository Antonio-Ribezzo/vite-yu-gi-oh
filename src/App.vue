<script>
  import axios from 'axios';
  // importo il file store.js per poi renderlo disponibile dentro data()
  import {store} from './store.js'
  import headerComp from './components/headerComp.vue';


  export default{
    name: 'App',

    components: {
      headerComp
    },

    data(){
      return{
        store
      }
    },
    
    created(){
      this.activeApi()
    },

    methods:{
      activeApi(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=1')
        .then((res)=>{
          this.store.arrayCards = res.data.data
        })
      }
    }
  }

</script>

<template>

  <headerComp/>

  
</template>

<style lang="scss">
  // importo il foglio di stile principale
  @use './style/main.scss' as *;

</style>

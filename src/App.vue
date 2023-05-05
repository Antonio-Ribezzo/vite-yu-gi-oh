<script>
  // importo axios
  import axios from 'axios';
  // importo il file store.js per poi renderlo disponibile dentro data()
  import {store} from './store.js'
  // importo i componenti
  import headerComp from './components/headerComp.vue';
  import mainComp from './components/mainComp.vue';


  export default{
    name: 'App',

    components: {
      headerComp,
      mainComp
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
  
  <mainComp/>

  
</template>

<style lang="scss">
  // importo il foglio di stile principale
  @use './style/main.scss' as *;

</style>

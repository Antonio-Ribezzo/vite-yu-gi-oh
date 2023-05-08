<script>
  // importo axios
  import axios from 'axios';
  // importo il file store.js per poi renderlo disponibile dentro data()
  import {store} from './store.js'
  // importo i componenti
  import headerComp from './components/headerComp.vue';
  import mainComp from './components/mainComp.vue';
  import selectComp from './components/selectComp.vue';


  export default{
    name: 'App',

    components: {
      headerComp,
      mainComp,
      selectComp
    },

    data(){
      return{
        store
      }
    },
    
    created(){
      this.activeGlobalApi(),
      this.activeArchetypesApi()
    },

    methods:{
      // activeGlobalApi(){
      //   axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=54')
      //   .then((res)=>{
      //     this.store.arrayCards = res.data.data
      //     console.log(res.data.data)
      //   })
      // },
      activeGlobalApi(){
        if(this.store.nomeArchetype == ''){
          axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=54`)
          .then((res)=>{
            this.store.arrayCards = res.data.data
            console.log(res.data.data)
          })
        } else {
          axios.get(` https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.nomeArchetype}`)
          .then((res)=>{
            this.store.arrayCards = res.data.data
            console.log(res.data.data)
          })
        }
      },

      activeArchetypesApi(){
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((res)=>{
          this.store.arrayArchetypes = res.data
          console.log(res.data)
        })
      }

    }
  }
</script>

<template>

  <headerComp/>

  <selectComp @search="activeGlobalApi"
  />
  
  <mainComp/>

  
</template>

<style lang="scss">
  // importo il foglio di stile principale
  @use './style/main.scss' as *;

</style>

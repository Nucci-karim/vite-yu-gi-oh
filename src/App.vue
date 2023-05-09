<script>
import HeaderComp from './components/HeaderComp.vue';
import Cards from './components/Cards.vue';
import axios from 'axios';
import {store} from './store';
import selectComp from './components/selectComp.vue';

export default{
  name: 'app',
  components:{
    HeaderComp,
    Cards,
    selectComp,
  },
  data(){
    return{
      store
    }
  },
  created(){
    this.chiamataApi()
  },
  methods: {
     chiamataApi(){
      if(store.archtypeValue !== ''){
        axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.archtypeValue}`)
           .then(res => {
             console.log(res.data.data)
             const datiApi = res.data.data
             this.store.arrayCards = datiApi
           })
      } else{
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=3')
           .then(res => {
             console.log(res.data.data)
             const datiApi = res.data.data
             this.store.arrayCards = datiApi
           })
      }
       
    },
  }
}
</script>

<template>
  <div id="tutto">
    <HeaderComp/>
    <main class="d-flex flex-column text-center justify-content-center p-5">
      <selectComp @nomeEmit="chiamataApi()" class="align-self-start m-3"/>
      <Cards/>
    </main>
  </div>
  
  
</template>

<style lang="scss">
@use './style/main.scss' as *;

#tutto{
height: 100vh;
}

main{
  background-color: rgb(212 143 56);
}

</style>

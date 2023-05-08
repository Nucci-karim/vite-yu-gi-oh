<script>
import HeaderComp from './components/HeaderComp.vue';
import Cards from './components/Cards.vue';
import axios from 'axios';
import {store} from './store';

export default{
  name: 'app',
  components:{
    HeaderComp,
    Cards,
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
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=3')
          .then(res => {
            console.log(res.data.data)
            const datiApi = res.data.data
            this.store.arrayCards = datiApi
          })
    },
  }
}
</script>

<template>
  <div id="tutto">
    <HeaderComp/>
    <main class="d-flex text-center justify-content-center p-5">
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

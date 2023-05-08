<script>
import card from './card.vue'
import {store} from '../store'

export default{
  name: 'Cards',
  components: {
    card,
  },
  data(){
    return{
      store
    }
  },
  
}
</script>

<template>
  <div id="cards" class="">
      <card 
      v-for="(elem, index) in store.arrayCards"
      :key="index"
      :dettagli="elem"
      />
  </div>
</template>

<style lang="scss" scoped>
#cards{
  background-color: white;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}

</style>
<script>
import axios from 'axios';
import {store} from '../store'

export default{
  name: 'selectComp',
  components: {
    
  },
  data(){
    return{
      store
    }
  },
  created(){
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
    .then( (res) => {
        console.log(res.data)
        store.arrayArchtype = res.data
    })
  },
  computed: {

  },
  
}
</script>

<template>
  <div id="" class="">
    <select name="select-cards" id="select-cards" v-model="store.archtypeValue" @change="$emit('nomeEmit')">
        <option :value="elem.archetype_name" v-for="(elem, index) in store.arrayArchtype" :key="index">
            {{ elem.archetype_name }}
        </option>
    </select>
  </div>
</template>

<style lang="scss" scoped>

</style>
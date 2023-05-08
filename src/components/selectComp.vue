<script>
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
  computed: {

  },
  
}
</script>

<template>
  <div id="" class="">
    <select v-model="selected">
        <option disabled value="">select one</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>
  </div>
</template>

<style lang="scss" scoped>

</style>
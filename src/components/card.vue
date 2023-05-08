<script>

export default{
  name: 'Card',
  props: [
    'dettagli',
  ],
  components: {
    
  },
  
}
</script>

<template>
  <div id="card" class="card">
    <img :src="dettagli.card_images[0].image_url" alt="foto">
    <div class="card-body">
        <h4 class="card-title">{{dettagli.name}}</h4>
        <span class="card-text">{{dettagli.archetype}}</span>
    </div>
    
  </div>
</template>

<style lang="scss" scoped>
#card{
    width: calc(100% / 6) ;
    margin: 0.5rem;
    .card-body{
        background-color: rgb(212 143 56);
    }
}

</style>
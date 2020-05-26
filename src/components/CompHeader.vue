<template >
  <div class="header">
   <header><h1>----{{titleHeader}}----</h1></header>
    
  </div>
  
</template>

<script>
export default {
  name: 'comp-header',
  props:{
    titleHeader: String,
  },
  data () {
    return {
     
    }
  }
}
</script>

<style lang="scss">
  .header{
    border: 2px solid;
  }


</style>

<template>
 <div class="footer">
   <header><h1>----{{titleFooter}}----</h1></header>
    
  </div>
</template>

<script>
export default {
  name: 'comp-footer',
  props:{
    titleFooter : String,
  },
  data () {
    return {
     
    }
  }
}
</script>

<style lang="scss">
   .footer{
    border: 2px solid;
     }


</style>

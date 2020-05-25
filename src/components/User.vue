<template>
   <div class="user">
       <h3>{{user.fullname}}</h3>
      
       
   </div>
</template>

<script>
export default {
  name: 'user',
  props:{
      user :{
          type :Object,
          default:null
      } ,
  },
  data () {
    return {
     
    }
  }
}
</script>

<style lang="scss">
  .user{
      background: wheat
     

  }


</style>

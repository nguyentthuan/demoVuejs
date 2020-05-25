<template>
   <div class="list-user" >
       
        <user v-for="(user,i) in listUser" 
              v-bind:key="i"
              v-bind:user="user"/>      
   </div>
</template>

<script>
import User from "./User"
export default {
  name: 'list-user',
  props: {
    listUser :{
        type: Array,
        default: []
    }
   
  },
  data () {
    return {
      
    }
  },
  components:{
      User
  }
}
</script>

<style lang="scss">
  .list-user{
     background: grey;
     padding: 2px;
     margin: 2px;
     p {
         color: orange;
        
     }

  }


</style>

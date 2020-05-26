<template>
   <div class="user">
       <h3>{{user.fullname}}</h3>
       <h4>{{user.phone}}</h4>
       <button class="delete" v-on:click="deleteUser">X</button>
      
       
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
  },
  methods:{
    deleteUser(){
      this.$emit("deleteEvent");
    }

  }
}
</script>

<style lang="scss">
  .user{
    position: relative;
    .delete{
      position: absolute;
      top: 0px;
      right: 0px;
      background: rgb(240, 82, 82)
    }

  }


</style>

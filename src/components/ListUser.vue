<template>
  <div class="list-user">
    <user v-for="(user, index) in listUser" v-bind:key="index" v-bind:user="user" v-on:deleteEvent="deleteEvent(index)" />
  </div>
</template>

<script>
import User from "./User";
export default {
  name: "list-user",
  props: {
    listUser: {
      type: Array,
      default: []
    }
  },
  data() {
    return {};
  },
  methods:{
    deleteEvent(data){
      console.log("ListUser data :" + data); // lây data từ comp User lên thông wa tham số data.
      
      this.$emit("deleteUserEvent",data);
    }
  },
  components: {
    User
  }
};
</script>

<style lang="scss">
.list-user {
  background: rgb(194, 181, 181);
  padding: 10px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  
  .user {
    padding: 20px;
    margin-bottom: 20px;
    background: wheat;
    border: 1px solid;
    width: 290px;
    height: 100px;
   
    
  }
}
</style>

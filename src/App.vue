<template>
  <div id="app">
    
    <div class="container">
      <comp-header  />  
      <div class="group1">
           <div class="input-them">
                <input  ref="inputName" class=" mr-sm-2" type="text" size="25" placeholder="Username" >
                <input  ref="inputPhone" class=" mr-sm-2" type="text" size="12" placeholder="PhoneNumber" >
                <button class="btn btn-outline-success my-2 my-sm-0"   v-on:click="addUser">ADD</button>
           </div>    
      </div>
         
      <div class="list-user">
           <list-user v-bind:listUser="listUser" v-on:deleteUserEvent="deleteUser"/>

      </div>
      
    </div>
    
   
  </div>
</template>

<script >
//import {Component,Props,Vue} from "vue-property-decorator"
import CompHeader from "./components/CompHeader";
import ListUser from "./components/ListUser";

export default {
  name: "app",
  data() {
    return {
     
      listUser: [
        { fullname: "Thuan Nguyen", phone: '0798742876'},
        { fullname: "Sir Alex", phone: '0384562876' },
        { fullname: "Vu nguyen", phone: '0382233445' },
        { fullname: "Thien Vo", phone: '0388742876' },
        { fullname: "Tien Minh", phone: '0224562876' },
        { fullname: "Lee Chen Wei", phone: '0904562876' },
        { fullname: "Chen Long", phone: '0388742876' },
        { fullname: "Lin Dan", phone: '0902562333' },
         { fullname: "Morata ", phone: '098874284' },
      ]
    };
  },
  methods:{
    deleteUser(index){
       this.listUser.splice(index,1);
    },
    addUser(e){
      var newName = this.$refs.inputName.value;
      var newPhone = this.$refs.inputPhone.value;
      var newUser = {fullname:newName,phone:newPhone}

      this.listUser.push(newUser);

     // console.log("addUser:" + this.$refs.inputThem.value)

    }

  },
  components: {
    CompHeader,
    ListUser
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  .container {
    max-width: 1170px;
    margin: 0 auto;
    padding: 0 15px;
    max-height: 3000px;
    .input-them{
      margin: 7px;
      width: 550px;
      float: right;
    }
    .group1:after{
      clear: both;
      content: ".";
      display: block;
      width: 0px;
      height: 0px;
        }
  }
}
</style>

<template>
  <div id="app">
    <comp-header v-bind:titleHeader="titleHeader" />
    <div class="container">
      <div class="inputthem">
        <input  ref="inputName" type="text" size="33" placeholder="Username.." >
        <input  ref="inputPhone" type="text" size="15" placeholder="PhoneNumber.." >
        <button @click="addUser">ADD</button>
      </div>
      
      <br><br>
      <list-user v-bind:listUser="listUser" v-on:deleteUserEvent="deleteUser"/>
    </div>
    <comp-footer v-bind:titleFooter="titleFooter" />
  </div>
</template>

<script>
import CompHeader from "./components/CompHeader";
import CompFooter from "./components/CompFooter";
import ListUser from "./components/ListUser";

export default {
  name: "app",
  data() {
    return {
      titleHeader: "Hello Header",
      titleFooter: "Hello Footer",
      username : '',
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
    CompFooter,
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
    .inputthem{
      margin: 7px;
      width: 550px;
      float: right;
      background: rgb(116, 174, 240)
    }
  }
}
</style>

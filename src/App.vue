<template>
  <div id="app">
    <comp-header v-bind:titleHeader="titleHeader"/>
    <div class="container">
        <img src="./assets/logo.png">
        <list-user v-bind:listUser="listUser"/>
    </div>
       
    <comp-footer v-bind:titleFooter="titleFooter"/>
    
  </div>
</template>

<script>
import CompHeader from "./components/CompHeader"
import CompFooter from "./components/CompFooter"
import ListUser from "./components/ListUser"

export default {
  name: 'app',
  data () {
    return {
      titleHeader : "Hello Header",
      titleFooter : "Hello Footer",
      listUser :[
        {fullname : 'Thuan nguyen',active : true},
        {fullname : 'Alexx',active : true},
        {fullname : 'Vu nguyen',active : false},
        {fullname : 'Thi Vo',active : true},
        {fullname : 'lan nguyen',active : false},

      ]

     
    }
  },
  components:{
    CompHeader,
    CompFooter,
    ListUser
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}


</style>

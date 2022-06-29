<template>
  <div id="app">

    <h2> {{ title }}</h2>
    <NavbarPart></NavbarPart>
    <AllFriends :friends="friends" @delete="deleteFriend"></AllFriends>
    <OnlineFriends :friends="friends"></OnlineFriends>

  </div>
</template>

<script>

import NavbarPart from './components/NavbarPart.vue'
import AllFriends from './components/AllFriends.vue'
import OnlineFriends from './components/OnlineFriends.vue'

export default {
  name: 'App',
  data(){
    return {
      title: 'Wow our vue website are running',
      
        friends:[
                    {name: 'A', online:false },
                    {name: 'B', online:false },
                    {name: 'C', online:true },
                    {name: 'D', online:true },
                    {name: 'E', online:false }
                ]

    }

  },
  components:{
    NavbarPart, 
    AllFriends, 
    OnlineFriends
  },
  methods:{
    deleteFriend(payload){
      //console.log(payload)
      this.friends = this.friends.filter(friend =>{
        return friend.name  !== payload.name

      })


    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

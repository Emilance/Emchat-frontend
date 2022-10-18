<script >
import {RouterView}   from  "vue-router"
import ChatPage from './components/ChatPage.vue'
import UserLogIn from './components/UserLogIn.vue';




export default {
   
    components: { ChatPage, UserLogIn }
}
      
    


</script>

<template>
  <div class="container">
    <!-- <router-view></router-view> -->
         <!-- <ChatPage/> -->
         <!-- <UserLogIn/> -->
         <RouterView/>
  </div> 
</template>

<style >
 
  
</style>

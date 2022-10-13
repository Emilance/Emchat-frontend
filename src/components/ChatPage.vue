
<script>
import Header from "./chatCompnents/Header.vue"
import Footer from "./chatCompnents/Footer.vue"
import SideHeader from "./sideBar/SideHeader.vue"
import Search from "./sideBar/Search.vue"
import Friend from "./sideBar/Friend.vue"
import ChatArena from "./chatCompnents/ChatArena.vue"

 
export default {
     data(){
        return{
            userInfo: [
                 { 
                    username :"Eminence",
                    lastMessage: "how are you doing ?",
                    picsurl :"/user1.png",
                    missedMessage : 1,
                    time: "6:00AM"
                 },
                 { 
                    username :"Peter",
                    lastMessage: "I have gone home",
                    picsurl :"/user2.jpg",
                    missedMessage : 2,
                    time: "8:52pM"
                 },
                 { 
                    username :"El John",
                    lastMessage: "I amhungry pls, can u send money?",
                    picsurl :"/user1.png",
                    missedMessage : 7,
                    time: "1:40AM"
                },

            ]
           
        }
     },
    components: { Header, Footer, SideHeader, Search, Friend, ChatArena }
}
        


</script>

<template> 
     <div class="container">
        <div class="sidebar">
            <SideHeader/>
            <Search/>
            <Friend  v-for="info in userInfo"  :username="info.username" 
            :lastMessage="info.lastMessage"
            :picsurl = "info.picsurl"
            :missedMessage="info.missedMessage"
            :time ="info.time"
            />
        </div>
        <div class="chatarea">
            <Header />
            <ChatArena/>
            <Footer/>
        </div>

     </div>

</template>

<style>
  .container {
    color:white;
    height: 100vh;
    width: 100%;
    display: flex;
  
  }
  .chatarea{
    flex: 1;
}
.sidebar{
    flex:0.4 ;
    background-color: rgb(90, 63, 116);
  }
  @media (max-width:700px) {
    .chatarea{
      display: none;
     }
     .sidebar{
    flex:1 ;
    background-color: rgb(90, 63, 116);
  }
  }
  
</style>
<template>
    <div   class="userlogin">
        <h1 class="logintitle">Welcome To Emchat</h1>
        <p class="loginsubtitle">Let's help build your connection</p>
        <Login  v-if="displayloginform  === 'login'"  @send-message="changeForm"  />
        <SignUp   v-else-if ="displayloginform === 'signup'"   @send-message="changeForm"/>
        <Anonymous  v-else-if ="displayloginform === 'anonymous'"  @send-message="changeForm"/>
        
        
         
    </div>
</template>

<script>
import Login from './userLogin/Login.vue';
import SignUp from './userLogin/SignUp.vue';
import Anonymous from './userLogin/Anonymous.vue';
    export default {
     data(){
        return{
            displayloginform : "login"
        }
     },
     methods:  {
        changeForm(form){
        
                this.displayloginform =form
         
        } 
     },

    components: { Login, SignUp, Anonymous }
}
</script>

<style >
    .userlogin{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 100vh;
    }
    .logintitle{
        font-weight: 900;
        font-size: 2.5rem;
    }
    .loginsubtitle{
        margin-bottom: 2rem;
    }
</style>
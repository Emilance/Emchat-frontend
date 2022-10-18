<template>
    <form  class="loginform">
        <div class="formfield">
            <input type="text" v-model="email"  placeholder="Email address"/>
        </div>
        <div class="formfield" >
            <input type="password" v-model="password" placeholder="Enter your password"/>
        </div>
        <input @click="onSubmit" type="submit" value="Login">
        <hr class="divider"/>
        <button @click="toggleform"   v-on:click.prevent="$emit('send-message', 'signup')">Register Here </button>
        <div class="links">
            <a href="/">
                Forgot Password
            </a> <span> | </span>
            <a href="/"   v-on:click.prevent="$emit('send-message', 'anonymous')">
                Join a chat group anonymously
            </a>
        </div>
    </form>
</template>

<script>
    export default {
        data(){
            return{
               
                email:'',
                password:''
            }
        },
        methods:{
            onSubmit(e){
                e.preventDefault()
                if(!this.email || !this.password){
                    alert("kinldy fill all input correctly")
                    return
                }
                const loginInfo ={
                    email : this.email,
                    password: this.password
                }
                console.log(loginInfo)
            },
          
        }
    }
</script>

<style>
    .loginform{
        background-color: aliceblue;
        height: 20rem;
        width: 30rem;
        display: grid;
        align-content: center;
        border-radius: 1rem;
    }
    .loginform > input, .loginform> button{
        height: 2.5rem;
        width: 85%;
        margin: auto;
        background-color:blueviolet ;
        border: none;
        color: white;
        font-weight: 600;
        border-radius: 5px;
        cursor: pointer;
    }
    .loginform > input:hover, button:hover{
        background-color:  rgb(90, 63, 116);
    }
    .formfield{
        height: 3rem;
        width: 85%;
        margin: auto;
    }
    .formfield>input{
        height: 2.5rem;
        width: 100%;
        padding-left: 1rem;
        font-size: 0.9rem;
        border-radius: 5px;
        background-color: white;
        border: none;
        border: 1px solid rgba(70, 65, 65, 0.432);
    }
   
    .divider{
        background-color:rgba(49, 48, 48, 0.411);
        width: 85%;
        font-size: 0.5rem;
        margin:1rem auto;
    }
    .links{
        font-size: 0.7rem;
        width: 85%;
        margin: 0.4rem auto;
        display: grid;
        grid-template-columns: 1.4fr 0.6fr 2fr;
    }
    .links> a{
        text-decoration: none;
        color: purple;
        font-weight: 600;
        text-align: center;

    }
    .links>span {
        color: purple;
        font-weight: 600;
    }
    .links> a:hover {
        color: black;
        background-color: transparent;
        font-weight: 600;
    }


</style>
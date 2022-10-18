<template>
    <form  class="signupform">
        <i class="fa fa-arrow-left" aria-hidden="true"></i>
       <div class="ufield  dfield">
        <input  v-model="firstName"  placeholder="firstName"/>
        <input v-model="lastName" placeholder="LastName"/>
       </div>
       <div class="ufield">
        <input v-model="email" placeholder="email address"/>
       </div>
       <div class="ufield">
        <input v-model="phone" placeholder="phone number" number/>
       </div>
       <div class="ufield">
         <select v-model="selected" options="genderoptions" >
            <option value="male">Male</option>
            <option value="female"> Female</option>
         </select>
       </div>
       <input  @click="onSubmit" type="submit" value="register"/>
       <button   v-on:click.prevent="$emit('send-message', 'login')">Login  here</button>
       <div class="links">
            <a href="/">
                Forgot Password
            </a> <span> | </span>
            <a href="/"   v-on:click.prevent="$emit('send-message', 'anonymous')" >
                Join a chat group anonymously
            </a>
        </div>
    </form>
</template>

<script>
    export default {
        data(){
            props:{
             method:{type: Function}
            }
            return{
             firstName:"",
             lastName:"",
             email:'',
             phone:'',
             genderoptions:[
                 { text: 'Male', value:'male'},
                 { text: 'Female', value:'femalemale'}
                ],
           
                
            }
        },
        methods:{
          onSubmit(e){
            e.preventDefault()
            if(!this.email){
                alert("Email is required")
                return
            }
            const NewUser = {
                id :Math.floor(Math.random() * 100000),
                firstName:this.firstName,
                lastName : this.lastName,
                email: this.email
            }
            console.log(NewUser)
             this.$emit("add-user", NewUser)
             this.firstName= '',
             this.lastName ='',
             this.email= ''

          }
        }
    }
</script>

<style >
 .signupform{
        background-color: aliceblue;
        height: 22rem;
        width: 30rem;
        display: grid;
        align-content: center;
        border-radius: 1rem;
    }
    .dfield{
        display: flex;
    }
    .ufield{
        height: 3rem;
        width: 85%;
        margin: 0.2rem  auto ;
    }
    .ufield> input,  .ufield> select {
        width: 100%;
        height: 2.3rem;
        padding:0  0.7rem;
        border-radius: 5px;
        border: 1px solid rgba(70, 65, 65, 0.432);
    }
    .signupform>input{
        width: 85%;
        margin: auto;
        height: 2.3rem;
        cursor: pointer;
        border: none;
        background-color:blueviolet ;
        color: white;
        font-weight: 600;
        border-radius: 5px;
    }
    .signupform>input:hover{
        background-color:  rgb(90, 63, 116);
    }
    .signupform > button{
        width: 85%;
        margin:0.8rem auto;
        height: 2.3rem;
        cursor: pointer;
        border: none;
        background-color:green;
        color: white;
        font-weight: 600;
        border-radius: 5px;
    }
    .fa-arrow-left{
        color:black;
        margin:0 0.8rem;
        cursor: pointer;
    }
    .fa-arrow-left:hover{
        transform: scale(1.01);
    }

</style>
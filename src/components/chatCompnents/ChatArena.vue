<script>

</script>

<template>
 <div class="chatarena">
        <div class="message">
            <div class="messagebody">
               <p class="text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Laboriosam, voluptatem.</p>
                <p>6:00am</p>
            </div>
        </div>
        <div class="sendermessage">
            <div class="sendermessagebody">
               <p class="text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Laboriosam, voluptatem.</p>
                <p>6:00am</p>
            </div>
        </div>
 </div>

</template>

<style>
.chatarena{
     background-color: black;
     display: fixed;
     height: 80vh;
     overflow-y: scroll;
}
.message{
    height:fit-content;
    width: 100%;
    border-top: 1px solid rgba(167, 167, 167, 0.555);
    padding: 0.7rem;
    display: flex;
    justify-content: flex-end;
}
.sendermessage{
    height:fit-content;
    width: 100%;
    border-top: 1px solid rgba(167, 167, 167, 0.555);
    padding: 0.7rem;
    display: flex;
    justify-content: flex-start;
}
.messagebody{
    width: 40%;
    height: fit-content;
    background-color: rgb(235, 42, 235);
    padding:0.7rem;
    border-radius: 1rem;
 
}
.sendermessagebody{
    width: 40%;
    height: fit-content;
    background-color: rgb(20, 14, 20);
    padding:0.7rem;
    border-radius: 1rem;
 
}
.messagebody> p{
    font-size: 0.6rem;
    margin:0.3rem;
}
.messagebody >.text{
    font-size: 0.8rem;

}

.sendermessagebody> p{
    font-size: 0.6rem;
    margin:0.3rem;
}
.sendermessagebody >.text{
    font-size: 0.8rem;

}
</style>
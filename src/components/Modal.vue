<template>
    <div class="Modal" :class="[theme=='light'?'light':'',theme=='dark'?'dark':'']">
        <p class="close text" @click.self="closeModal">&times;</p>
        <h2>Hello, this is a Modal </h2>
        <p>Lorem ipsum is a placeholder text </p>
        <p class='changeTheme text' @click="changeTheme">Change theme</p>
        <div class="btns">
            <button class="btn btn-outline-primary">Sign up</button>
            <button class="btn btn-outline-primary mx-3">Log in</button>
        </div>
    </div>
</template>
<script>
    export default {
        name:'Modal',
        props:['theme'],
        methods:{
            closeModal(){
                this.$emit('close');
            },
            changeTheme(){
                this.$emit('change')
            }
        }
    }
</script>
<style scoped>
   .Modal{
    width: 400px;
    margin: auto;
    text-align: center;
    background-color: white;
    box-shadow: 0 0 10px #ddd;
    border-radius:10px;
    padding: 30px;
    position: absolute;
    top: 200px;
    left: 50%;
    transform: translate(-50%,-50%);
    transition: 1s;
   }
   h2{
    color:rgb(76, 181, 155);
    margin-top:-30px
   }
   p{
    color: #5e5e5e;
   }
   .text{
    cursor: pointer;
    color: #5e5e5e;
   }
   .text:hover{
    color:rgb(76, 181, 155);
   }
   .light{
    background-color: #fff;
   }
   .dark{
    background-color: #212121;
   }
   .dark p{
    color: #d5d5d5;
   }
   .close{
    font-size: 25px;
    text-align: end;
    position: relative;
    left:330px;
    top:-15px;
    width: 20px;
   }
   .changeTheme{
    width: 110px;
    margin: auto;
    margin-top: -10px;
    margin-bottom: 20px;;
   }
   .btns button{
    border:1px solid rgb(76, 181, 155) !important;
    color:rgb(76, 181, 155) !important ;
    height: 40px;
    width: 80px;
   }
   .btns button:hover{
    background-color: rgb(76, 181, 155) !important;
    color: #fff !important;
   }
</style>
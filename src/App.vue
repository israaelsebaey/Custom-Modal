<template>
  <div class="container">
    <h4 class="my-3">Welcome in my website):</h4>
    <div v-if="showModal">
      <Modal @close="toggleModal" :theme="modalTheme" @change="changeTheme"/>
    </div>
    <button class="btn btn-outline-success" @click="toggleModal">Open Modal</button>
  </div>
</template>
<script>
  import Modal from './components/Modal.vue';
  export default {
    name: 'App',
    data:()=>({ 
      showModal:false,
      modalTheme:'light'
    }),
    methods:{
      toggleModal(){
        this.showModal=!this.showModal
      },
      changeTheme(){
        if(this.modalTheme=='light'){
           this.modalTheme='dark'
        }
        else if(this.modalTheme=='dark'){
          this.modalTheme='light'
        }
      }
    },
    components: {
      Modal
    }
  }
</script>
<style scoped>
  .container{
    text-align: center;
    margin-top: 100px;
  }
  button{
    margin: auto;
    border:1px solid rgb(76, 181, 155) !important;
    color: rgb(76, 181, 155) !important;
    transition: 0.5s;
    height: 40px;
  }
  button:hover{
    background-color: rgb(76, 181, 155) !important;
    color: #fff !important;
  }
</style>

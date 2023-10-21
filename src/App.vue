<template>
  <h1>I am no Jedi</h1>
  <h2>{{title}}</h2>
  <input type="text" ref="name">
  <button @click="handleClick">Don't Click</button>
  <Modal/>
</template>

<script>
import Modal from './components/Modal.vue'


export default {
  name: 'App',
  components:{Modal},

  
  data(){
    return{
      title:'This is the end for you my Master',
    }
  },
  methods:{
    handleClick(e){
      console.log(this.$refs.name.value)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()

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
h1{
  color:#e43121
}
.active{
  color:royalblue;
}
</style>

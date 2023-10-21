<template>
  <h1>I am no Jedi</h1>
  <h2>{{title}}</h2>
  <input type="text" ref="name">
  <button @click="handleClick">Don't Click</button>
  <teleport to=".modals" v-if="showModal">
    <!-- <Modal :header="header" :text="text" theme="sale" @close="toggleModal"/> -->
    <Modal  theme="sale" @close="toggleModal">
      <h1>Jedi Announcment</h1>
      <p>The Temple is under attack, do not return. Go into hiding. we must wait until a new hope emerges</p>
    
    <template v-slot:links>
      <a href="/">View videos</a><br/>
      <a href="/">View images</a>
    </template>
    </Modal>
    
  </teleport>
  <teleport to=".modals" v-if="darkModal">
    <Modal theme="dark" @close="reverseModal">
      <h1>Hello there</h1>
    </Modal>
  </teleport>
  <button @click="toggleModal">show Modal</button>
  <br/>
  <button @click="reverseModal">DO IT</button>

</template>

<script>
import Modal from './components/Modal.vue'


export default {
  name: 'App',
  components:{Modal},

  
  data(){
    return{
      title:'This is the end for you my Master',
      header:'Do you deiscard your old life?',
      text:'The start of something new',
      showModal:false,
      darkModal:false,
    }
  },
  methods:{
    handleClick(e){
      console.log(this.$refs.name.value)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()

    }
,
    toggleModal(){
      this.showModal=!this.showModal
    },
    reverseModal(){
      this.darkModal=!this.darkModal
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

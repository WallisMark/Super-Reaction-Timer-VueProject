<template>
  <h1>Super Reaction App</h1>
  <button @click = "handleStart">click</button>
  <BlockComponent/>
</template>

<script>
import BlockComponent from './components/BlockComponet.vue'

export default {
  name: 'App',
  components: {
    BlockComponent
  },
  data(){
    return{
      isPlaying:false,
      delay: null
    }
  },
  methods:{
    handleStart(){
      this.isPlaying = true
      this.delay = 2000 + Math.floor(Math.random()*5000)
      console.log(this.delay)
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
</style>

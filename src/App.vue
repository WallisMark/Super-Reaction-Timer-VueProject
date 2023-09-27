<template>
  <h1>Super Reaction App</h1>
  <button @click = "handleStart" :disabled = "isPlaying">click to start</button>
  <BlockComponent :delay="delay" v-if = "isPlaying" @end="handleEndGame"/>
  <p v-if ="showResults">reaction time:{{ score }} ms</p>
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
      delay: null,
      scole:null,
      showResults:null
    }
  },
  methods:{
    handleStart(){
      this.isPlaying = true
      this.delay = 2000 + Math.floor(Math.random()*5000)
      console.log(this.delay)
    },
    handleEndGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
      this.showResults= true

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

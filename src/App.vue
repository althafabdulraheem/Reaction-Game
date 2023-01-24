<template>
  <h1>Welcome to G A M Eeee ....</h1>
  <button @click="start" v-bind:disabled="play">Play</button>
  <div v-if="play">
    <Block  :delay="delay" @end="endGame"/>

  </div>
  <Result  v-if="showResults" :score="score"/>
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'

export default {
  components:{Block,Result},
  data()
  {
    return{
      play:false,
      delay:null,
      score:null,
      showResults:false
    }
  },
  
   methods:{
     start()
     {
       this.play=true,
       this.delay=2000+Math.random()*5000
       console.log(this.delay)
       this.showResults=false

      
     },endGame(reactionTime)
     {
       this.score=reactionTime
       this.showResults=true
       this.play=false

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
button{
  background:#0faf87;
  color:white;
  border:none;
  padding:20px;
  font-size:16px;
  letter-spacing:1px;
  cursor:pointer;
  margin:10px;
  font-weight: bold;
}
button[disabled]
{
  cursor:not-allowed;
}
</style>

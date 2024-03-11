<template>
    
      <h1>How fast can you catch me??!</h1>
    <button v-on:click="startGame" :disabled="clPlay">Play</button>
    <div v-if="clPlay">
      <Block v-bind:delaying="delay" v-on:scoring="endGame"></Block>
    </div> 
    <div v-if="resultText">
      <Result v-bind:fScore="scores"></Result>
    </div>
     
  
  
</template>

<script>

import Block from "./components/Block.vue";
import Result from "./components/Result.vue";

export default {
  data(){
    return{
      clPlay:false,
      delay:null,
      scores:0,
      resultText:false
    }
  },
  methods:{
    startGame(){
      this.clPlay=true;
      this.delay=2000+Math.random()*5000;    
    },

    endGame(scored){
      this.scores=scored;
      this.clPlay=false;
      this.resultText=true;
    }
    
  },
  components: {
    Block:Block,
    Result:Result,
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
body{
  background-color: dimgray;
  margin: 0;
}
</style>

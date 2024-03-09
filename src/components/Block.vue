<template>
  <div class="blockStyle" v-if="showBlock" v-on:click="stopTimer">
    <h3>Click Me!!!</h3>
  </div>
  
</template>

<script>
export default {

    props:["delaying"],

    data(){
      return{
        showBlock:false,
        score:0,
        Time:null
        
      }
    },

    mounted(){
      setTimeout(() => {
        this.showBlock=true;
        this.startTimer();
      }, this.delaying);
    },

    methods:{
      
      startTimer(){
        this.Time=setInterval(()=>{
          this.score+=50;
          // console.log(this.score);
        },50);
      }, 
      
      stopTimer(){
        clearInterval(this.Time);
        this.$emit("scoring",this.score);
      }
    }

    // updated(){
    //   console.log("Updating done!!");
    // },

    // unmounted(){
    //   console.log("It's unmounted...");
    // }
}
</script>

<style>
    .blockStyle{
        width: 400px;
        height: 200px;
        background-color: darkolivegreen;
        margin: 30px auto;
        padding: 20px;
        color: aliceblue;
        border-radius: 10px;

    }
</style>
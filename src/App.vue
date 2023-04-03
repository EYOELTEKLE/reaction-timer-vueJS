<script >
import Block from './components/Block.vue';
import Results from './components/Results.vue';
  export default
  {
    name:'App',
    components:{Block,Results},
    data()
    {
        return  {
          isPlaying:false,
          delay:null,
          score:null,
          showResults:false,
        }
    },
    methods:
    {
      start()
      {
        this.isPlaying = true;
        this.delay = 2000 + Math.random() * 5000;
        this.showResults = false
       
      },
      endGame(reactionTime)
      {
          this.score = reactionTime;
          this.isPlaying = false
          this.showResults = true;
      }
    }
  }
</script>

<template>
  <div class="container">
    <h1>Reaction Timer Project </h1>
    <button @click="start" v-if="!isPlaying">Play</button>
    <Block v-if="isPlaying" :delay="delay" :isPlaying="isPlaying" @end="endGame"/>
    <Results v-if="showResults" :score="score"/>
  </div>
  
</template>

<style scoped>
h1
{
text-align: center;
color:var(--color-blue);
margin-top:25px;
text-transform: uppercase;
}
button
{
  border: 2px solid blueviolet;
  border-radius: 500px;
  width:80px;
  height: 33px;
  background-color: green;
  color:pink;
  display: block;
  margin:0 auto;
 
  
  transition-duration: 1s;
  transition-timing-function: linear;
  transition-delay: 1s;
  
}
button:hover
{
  background:yellow;
  color:black;
}
button:active
{
  transition:none;
  border:3px solid black;
  background-color: red;
}
p
{
  text-align: center;
}

</style>

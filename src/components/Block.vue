<template >
    <div v-if="show" @click="stopTimer">
        click me
    </div>
</template>
<script>
export default {
    props:['delay','isPlaying'],
    mounted()
    {
        setTimeout(() => 
        {
            this.show = true;
            this.startTimer();
        },
        this.delay)
    },
   data()
   {
     return {
        show:false,
        timer:null,
        reactionTime:0,
     }
   },
   methods:
   {
     startTimer() {
       this.timer = setInterval(() => 
       {
        this.reactionTime += 10
       },10);
     },
     stopTimer() {
        clearInterval(this.timer);
        this.$emit('end',this.reactionTime)
     }
   }
    
}
</script>
<style scoped>
    div
    {
        margin: 14px auto;
        height:100px;
        width:250px;
        background: red;
        color:black;
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>
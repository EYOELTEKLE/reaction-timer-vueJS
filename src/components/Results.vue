<template >
    <div>
        <p>Reaction Time:  {{ score }}ms</p>
       <p>you are {{ rank }}</p>
    </div>
</template>
<script>
export default {
    props:['score'],
    data(){
        return {
            rank:null
        }
    },
    mounted()
    {
        if(this.score < 250)
        {
            this.rank = "alien !"
        }
        else if(this.score < 400)
        {
            this.rank = "Fast !"
        }
        else
        {
            this.rank = "slow as a snail!"
        }
    }
}
</script>
<style >
    p
    {
        text-align: center;
    }
</style>
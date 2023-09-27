<template>
    <div class="block" v-if ="showBlock" @click="stopTimer" >
        click me
    </div>
</template>

<script>
export default {
props:["delay"],
data(){
    return{
        showBlock:false,
        timer:null,
        reactionTime:0
    }
},
mounted(){
    console.log("mounted to the dom")
    setTimeout(()=>{
        this.startTimer()
        this.showBlock = true
    },this.delay)

},
methods:{
    startTimer(){
        this.timer = setInterval(()=>{
            this.reactionTime +=10
        },10)
    },
    stopTimer(){
        clearInterval(this.timer)
        console.log(this.reactionTime)
    }
}
}
</script>

<style>
.block{
    width: 400px;
    border-radius:20px;
    background:#0faf87;
    color:white;
    text-align: center;
    padding: 108px;
    margin: 48px auto;
}

</style>
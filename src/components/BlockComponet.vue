<template>
    <div class="block" v-if ="showBlock" >
        click me
    </div>
</template>

<script>
export default {
props:["delay"],
data(){
    return{
        showBlock:false
    }
},
mounted(){
    console.log("mounted to the dom")
    setTimeout(()=>{
        this.showBlock = true
        console.log(this.delay)
    },this.delay)

},
updated(){
    console.log("updated")
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
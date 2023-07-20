<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="block" v-if="showblock" @click="stopTimer">Click here</div>
</template>

<script>
export default {
    data() {
        return {
            showblock:false,
            timer:null,
            score:0,
        }
    },
    props:[
        'delay'
    ],
    mounted(){
        setTimeout(()=>{
            this.showblock=true,
            this.startTimer()
        },this.delay);
    },
    methods:{
        startTimer(){
            this.timer=setInterval(()=>{
                    this.score+=50
                },50); 
        },
        stopTimer(){
            clearInterval(this.timer)
            this.$emit("endGame",this.score)
        }
    }
    
}
</script>

<style>
    .block{
        background-color: aquamarine;
        widows: 400px;
        height: 300px;
        padding-top: 30px;
        margin: 20px auto;
    }
</style>
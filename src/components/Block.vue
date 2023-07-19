<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="block" v-if="showblock">Click here</div>
</template>

<script>
export default {
    data() {
        return {
            showblock:false
        }
    },
    props:[
        'delay'
    ],
    mounted(){
        setTimeout(()=>{
            this.showblock=true
        }, this.delay)
    },
    updated(){
        console.log("updated")
    },
    unmounted(){
        console.log("unmounted")
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
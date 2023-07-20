<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <p> Result is: {{ score }} ms </p>
  <div v-if="score<250">
    <p>You are fast</p>
  </div>
  <div v-else-if="score>250 && score<500">
    <p>You are normal</p>
  </div>
  <div v-else>
    <p>You are slow</p>
  </div>
</template>

<script>
export default {
    props:['score']
}
</script>

<style>
    p{
        color: red;
    }
</style>
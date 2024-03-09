<template>
  <p>The Result : {{fScore}}</p>
  
  <div v-if="fScore<=250">
    <p>You are too fast, Great Job!!!</p>
  </div>
  <div v-else-if="fScore>250 && fScore<=400">
    <p>You are normal...</p>
  </div>
  <div v-else>
    <p>You are too slow, Try again!!!</p>
  </div>
</template>

<script>
export default {
    props:["fScore"],
}
</script>

<style>

</style>
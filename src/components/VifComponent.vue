<script>
export default {
  name: "VifComponent",
  props:{
    bool: Boolean
  },
}
</script>

<template>
  <div>
    <h1>V-IF</h1>
    <img v-if="bool" src="../assets/logo.svg" width="120px">
  </div>
</template>

<style scoped>

</style>
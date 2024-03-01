<script>
export default {
  name: "VshowComponent",
  props:{
    bool: Boolean
  },
}
</script>

<template>
<div>
  <h1>V-SHOW</h1>
  <img v-show="bool" src="../assets/logo.svg" width="120px">
</div>
</template>

<style scoped>

</style>
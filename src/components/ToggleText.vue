<script>
export default {
  name: "ToggleText",props:{
    bool: Boolean
  },
}
</script>

<template>
<h2>{{bool ? 'Повідомлення 1' : 'Повідомлення 2'}}</h2>
</template>

<style scoped>

</style>
<script setup>


function toto() {
  alert(2);
}
</script>

<template>
  <h1 @click="toto">Dany</h1>
</template>

<style scoped>
h1 {
  color: red;
}
</style>

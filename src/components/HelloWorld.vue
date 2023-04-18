<script setup>
import { ref } from 'vue';

defineProps({
  msg: String,
});

const tt = function(){
  alert(count.value);
  count.value = 15;
}
const count = ref(10);
</script>

<template>
  <h1 @click="tt">{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>

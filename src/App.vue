<script setup>
import Home from './components/Home.vue';
import Contact from './components/Contact.vue';
import Inconnu from './components/Inconnu.vue';
import { computed, ref, onMounted } from 'vue';

const infoHash = ref(window.location.hash);
const Route = ref({
  '/': Home,
  '/contact': Contact,
});

const currentView = computed(() => {
  return Route.value[infoHash.value.slice(1) || '/'] || Inconnu;
});

onMounted(() => {
  window.addEventListener('hashchange', () => {
    infoHash.value = window.location.hash;
  });
});
</script>

<template>
  <a href="#/"> Home </a> | <a href="#/contact"> Contact </a> |
  <a href="#/dfgdf"> inconnu </a>
  <hr />
  <component :is="currentView" />
</template>

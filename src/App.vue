<script setup>
import { useDark, useToggle, useColorMode } from '@vueuse/core';
const isDark = useDark(); // true or false
const colorMode = useColorMode({
  modes: {
    dim: 'dim',
    cafe: 'cafe',
  },
  attribute: 'theme',
}); // 'light' or 'dark'
const toggleDark = useToggle(isDark);
</script>

<template>
  {{ colorMode }}
  <button @click="colorMode = 'dark'">Dark Mode</button>
  <button @click="colorMode = 'light'">Light Mode</button>
  <button @click="colorMode = 'dim'">Dim Mode</button>
  <button @click="colorMode = 'cafe'">Cafe Mode</button>
  <button @click="toggleDark()">Toggle Dark</button>
</template>
<style>
[theme='dark'] {
  background: #252525;
  color: white;
}
[theme='dim'] {
  background: gray;
  color: white;
}
[theme='cafe'] {
  background: #c0acac;
  color: black;
}
</style>

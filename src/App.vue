<script setup lang="ts">
//@ts-ignore-line: 'HelloWorld' is declared but its value is never read.
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template lang="pug">
div
    a( href="https://vite.dev" target="_blank")
            img(src="/vite.svg" class="logo" alt="Vite logo")
    a(href="https://vuejs.org/" target="_blank")
        img(src="./assets/vue.svg" class="logo vue" alt="Vue logo")
    HelloWorld(msg="Vite + Vue")
</template>

<style scoped>
.logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
}
.logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
    filter: drop-shadow(0 0 2em #42b883aa);
}
</style>

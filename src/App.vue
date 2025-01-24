<script setup lang="ts">
//@ts-ignore-line: unused declaration, but used in Pug Template
import Intro from "./components/Intro.vue";
</script>

<template lang="pug">
div
    a( href="https://vite.dev" target="_blank")
            img(src="/vite.svg" class="logo" alt="Vite logo")
    a(href="https://vuejs.org/" target="_blank")
        img(src="./assets/vue.svg" class="logo vue" alt="Vue logo")
    HelloWorld(msg="Vite + Vue")
    Intro
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

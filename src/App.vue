<template lang="pug">
nav.nav: ul
	li(
		v-for="route in navRoutes"
		:class="{current: (currentPath.length > 2 && route.url.includes(currentPath.slice(1)) )}"
	)
		a(:href="route.url") {{ route.title }}
//- #component: component(:is="currentView")
#component
	Intro
	About
	Portfolio
	Resume

.right
	.color-mode
		label(for="#color-mode")
			span Dark/Light
		input(type="checkbox" id="color-mode")

	.social-links
		div: a.round-row.linkedin(href="https://linkedin.com" target="_blank")
			span LinkedIn
			span (IMG)
			img()
		div: a.round-row.github(href="https://github.com" target="_blank")
			span GitHub
			span (IMG)
			img()
</template>

<script setup lang="ts">

import { computed, ref, type Component } from "vue";

import Intro from "./components/Intro.vue";
import About from "./components/About.vue";
import Portfolio from "./components/Portfolio.vue";
import Resume from "./components/Resume.vue";
import NotFound from "./components/NotFound.vue";

type Routes = {
	[key: string]:{url: string, component: Component, title: string}
};

/**
 * Bare-bone routing from <https://vuejs.org/guide/scaling-up/routing.html>
 */
const currentPath = ref(window.location.hash);
const routes: Routes = {
	'/': {url: '#/', component: Intro, title: "Intro"},
	'/portfolio': {url: '#/portfolio', component: Portfolio, title: "Portfolio"},
	'/about': {url: '#/about', component: About, title: "About"},
	'/resume': {url: '#/resume', component: Resume, title: "Resume"},
	'/not-found': {url: '#/not-found', component: NotFound, title: "NotFound"},
};

/* @ts-ignore: currentView is "unused declaration" but used in Pug template */
const navRoutes: Routes = {
	'/': {url: '#/', component: Intro, title: "Intro"},
	'/portfolio': {url: '#/portfolio', component: Portfolio, title: "Portfolio"},
	'/about': {url: '#/about', component: About, title: "About"},
	'/resume': {url: '#/resume', component: Resume, title: "Resume"},
};

/* @ts-ignore: currentView is "unused declaration" but used in Pug template */
const currentView = computed(
	() => routes[currentPath.value.slice(1) || '/']?.component || NotFound
);

window.addEventListener('hashchange', () => {
	currentPath.value = window.location.hash;
})

</script>

<style lang="scss">



</style>

<template lang="pug">
nav.nav: ul
	li(
		v-for="route in navRoutes"
		:class="{current: (currentPath.length > 2 && route.url.includes(currentPath.slice(1)) )}"
	)
		a(:href="route.url") {{ route.title }}

#component
	Intro
	About
	Portfolio
	Resume

.right
	.social-links
		div: a.round-row.linkedin(href="https://www.linkedin.com/in/shandelle-leigh/" target="_blank")
			include ./assets/linkedin.pug
			span LinkedIn
		div: a.round-row.github(href="https://github.com/ShandelleLeigh" target="_blank")
			include ./assets/github.pug
			span GitHub
</template>

<script setup lang="ts">

	import { ref, type Component } from "vue";

	import Intro from "./components/Intro.vue";
	import About from "./components/About.vue";
	import Portfolio from "./components/Portfolio.vue";
	import Resume from "./components/Resume.vue";
	import NotFound from "./components/NotFound.vue";

	type Routes = {url: string, component: Component, title: string}[];

	const routes: Routes = [
		{url: '/#', component: Intro, title: "Intro"},
		{url: '/#portfolio', component: Portfolio, title: "Portfolio"},
		{url: '/#about', component: About, title: "About"},
		{url: '/#resume', component: Resume, title: "Resume"},
		{url: '/#not-found', component: NotFound, title: "NotFound"}
	];

	/* @ts-ignore: navRoutes is "unused declaration" but used in Pug template */
	const navRoutes: Routes = routes.filter(
		route => !route.url.includes('not-found') ? route : null
	);

	/**
	 * Bare-bone routing based on <https://vuejs.org/guide/scaling-up/routing.html>
	 */
	const currentPath = ref(window.location.hash);

	window.addEventListener('hashchange', () => {
		currentPath.value = window.location.hash;
	})

</script>
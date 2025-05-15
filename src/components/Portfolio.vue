<template lang="pug">
#portfolio
	div Portfolio
		div
			h2 Web Designs and Development


			div.g-cols-2
				h3 Olympus Business Capitol Home Page
				h4
					|
					a(
						target="_blank"
						href="https://olympusbusinesscapital.com/"
					)  Designed in Figma
					|
					| and
					|
					a(
						target="_blank"
						href="https://olympusbusinesscapital.com/"
					) built in Wordpress
				.col-2
					ExpandableSection(
					:item="figmaPreviews.olympus"
					@switch-state = "switchState"
				)

				h3 Canine Revolution Dog Training Home Page
				h4
					|
					a(
						target="_blank"
						href="https://olympusbusinesscapital.com/"
					)  Designed in Figma
					|
					| and
					|
					a(
						target="_blank"
						href="https://caninerevolutiondogtraining.com/"
					) built in Wordpress

				.col-2
					ExpandableSection(
						:item="figmaPreviews.canine"
						@switch-state = "switchState"
					)

		div
			h2 Illustrations
			div.g-cols-2
				a(
					target="_blank"
					href="https://medicaldecisions.info/"
				)
					h3 End of Life Medical Decisions

				.col-2
					ExpandableSection(
						:item="figmaPreviews.endgame"
						@switch-state = "switchState"
					)

		div
			h2 Other Web and App Development and some Design


</template>

<script setup lang="ts">
import { ref, type Ref } from 'vue';

/* @ts-ignore : used in Pug template */
import ExpandableSection from "./ExpandableSection.vue";


/* @ts-ignore: figmaPreviews is "unused declaration" but used in Pug template */
const figmaPreviews: Ref<{
	[key: string]: {name: string,state: boolean,src: string}
}> = ref({
	olympus: {
		name: "olympus",
		state: false,
		src: "https://www.figma.com/proto/HoEyw0gxKj3CLxbq5OmgCL/Portfolio-Designs?node-id=7-891&t=2UnPM0N52REiTY87-1&viewport=296%2C302%2C0.12&scaling=contain&content-scaling=fixed&embed-host=share"
	},
	canine: {
		name: "canine",
		state: false,
		src: "https://embed.figma.com/proto/HoEyw0gxKj3CLxbq5OmgCL/Portfolio-Designs?page-id=0%3A1&node-id=1-467&p=f&viewport=296%2C302%2C0.12&scaling=contain&content-scaling=fixed&embed-host=share",
	},
	endgame: {
		name: "endgame",
		state: false,
		src: "https://embed.figma.com/proto/3S2dvRS9xRqnSrzLozoZgu/FLW-illustrations?page-id=0%3A1&node-id=6-927&p=f&viewport=736%2C-561%2C0.1&scaling=scale-down&content-scaling=fixed&starting-point-node-id=6%3A927&embed-host=share",
	},
});

/* @ts-ignore: figmaPreviews is "unused declaration" but used in Pug template */
const switchState = (e: {name: string, state: boolean}) => {
	figmaPreviews.value[e.name].state = e.state;
}


</script>

<style lang="scss">

</style>

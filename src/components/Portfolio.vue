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
						:href="linksList.olympus.protoDesign"
					)  Designed in Figma
					|
					| and
					|
					a(
						target="_blank"
						:href="linksList.olympus.liveSite"
					) built in Wordpress
				.col-2
					//- ExpandableSection(
					//- 	:item="linksList.olympus"
					//- 	@switch-state="switchState"
					//- )

				h3 Canine Revolution Dog Training Home Page
				h4
					|
					a(
						target="_blank"
						:href="linksList.canine.protoDesign"
					)  Designed in Figma
					|
					| and
					|
					a(
						target="_blank"
						:href="linksList.canine.liveSite"
					) built in Wordpress

				.col-2
					//- ExpandableSection(
					//- 	:item="linksList.canine"
					//- 	@switch-state="switchState"
					//- )
					LazyLoad(
						:source="PATHS.CRDT.HOME_PAGE"
						alt="CRDT home page design preview"
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
					//- ExpandableSection(
					//- 	:item="linksList.endgame"
					//- 	@switch-state="switchState"
					//- )

		div
			h2 Other Web and App Development and some Design


</template>

<script setup lang="ts">
import { linksList } from '../data/portfolioLinks';

/* @ts-ignore : used in Pug template */
import ExpandableSection from "./ExpandableSection.vue";
/* @ts-ignore : used in Pug template */
import LazyLoad from "./LazyLoad.vue";

/* @ts-ignore : used in Pug template */
const PATHS = {
	CRDT:{
		HOME_PAGE: "/CRDT_home-page_compressed.jpg",
		TRAINING: "/CRDT_dog-training_compressed.jpg",
	}
};


/* @ts-ignore: linksList is "unused declaration" but used in Pug template */
const switchState = (e: {name: string, state: boolean}) => {
	linksList[e.name].state = e.state;
}


</script>

<style lang="scss">

</style>

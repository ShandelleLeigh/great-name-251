<template lang="pug">
.lazy-wraper()
	.skeleton-image( )
	img.skeleton-image(
		:data-url="source"
		:alt="altText"
		:src="source"
	)

</template>

<script setup lang="ts">
import {
	// computed,
	ref,
	// type Ref,
} from 'vue';

/* @ts-ignore: unused declaration(s) used in pug template */
const props = defineProps<{
	source: string,
	alt?: string,
}>();


/* @ts-ignore: unused declaration(s) used in pug template */
// const style: Ref<string> = ref(
// 	`height: ${
// 	(props?.style?.height !== "undefined") ? props?.style?.height + "px" : "1rem"
// 	}; width: ${
// 	(props?.style?.width !== "undefined") ? props?.style?.width + "px" : "1rem"
// 	};`
// )

console.log( "Did it load? ",   );
/* @ts-ignore: unused declaration(s) used in pug template */
const altText = ref(props.alt || "image with unset alt text. oops.");

</script>

<style lang="scss">
.lazy-wraper, .lazy-wraper .skeleton-image{
	max-width: 50vw;
}
</style>

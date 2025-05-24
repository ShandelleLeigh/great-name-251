<template lang="pug">
.lazy-wraper(
	:style="style"
)
	.skeleton-image( )
	img.skeleton-image(
		:data-url="source"
		:alt="altText"
		:src="source"
		:style="style"
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
	style?: {height?: number | string, width?: number | string },
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

console.log( "Did it load? ", style.value, props?.style?.height);
/* @ts-ignore: unused declaration(s) used in pug template */
const altText = ref(props.alt || "image with unset alt text. oops.");

</script>

<style lang="scss">
</style>

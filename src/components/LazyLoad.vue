<template lang="pug">
.lazy-wraper(
	v-lazyload
	:style="style"
)
	.skeleton-image( )
	img.skeleton-image(
		:data-url="source"
		:alt="altText"
	)

</template>

<script setup lang="ts">
import {
	ref, type Ref,
} from 'vue';

/* @ts-ignore: unused declaration(s) used in pug template */
const props = defineProps<{
	style?: {height?: number | string, width?: number | string },
	source: string,
	alt?: string,
}>();

/* @ts-ignore: unused declaration(s) used in pug template */
const style: Ref<string> = ref(
	`height: ${
		props?.style?.height + "px" || "1rem"
	}; width: ${
		props?.style?.width + "px" || "1rem"
	};`
)

/* @ts-ignore: unused declaration(s) used in pug template */
const altText = ref(props.alt || "image with unset alt text. oops.")

</script>

<style lang="scss">
</style>

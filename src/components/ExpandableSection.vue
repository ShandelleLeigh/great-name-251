<template lang="pug">
.expand()
	.button-like.tab(
		@click="emitSwitchState"
		:class="(state === true ? 'open' : 'closed')"
	)
		span Show Figma preview
		include ../assets/chevron-down.pug

	div.expandable(
		:class="(state === true ? 'expanded' : 'collapsed')"
	)
		iframe(
			style="border: 1px solid rgba(0, 0, 0, 0.1);border-radius:12px;"
			width="550"
			height="450"
			:src="src"
			allowfullscreen
		)

</template>

<script setup lang="ts">

import { computed, ref } from 'vue';

// //- div(@click="$emit('switchState', {name: name, state: !state })") Expand?

/* @ts-ignore: unused destructured elements are used in pug template */
const props = defineProps<{item: {state: boolean, src: string, name: string}}>();
const emit = defineEmits<{(e: 'switchState', value: {name: string, state: boolean}): void}>();

/* @ts-ignore: more items in the pug template */
const state = computed(()=>{return props.item.state});
/* @ts-ignore: more items in the pug template */
const src = ref(props.item.src);
/* @ts-ignore: more items in the pug template */
const name = ref(props.item.name);

/* @ts-ignore: unused destructured elements are used in pug template */
const emitSwitchState = () => {
	emit('switchState', {name: props.item.name, state: !props.item.state})
};

</script>

<style lang="scss">
// .expand{}
</style>

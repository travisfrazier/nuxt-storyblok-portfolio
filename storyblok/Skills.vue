<template>
	<section
		v-editable="blok"
		class="skills__section"
	>
		<StoryblokComponent
			v-for="blok in blok.columns"
			:key="blok._uid"
			:blok="blok"
		/>
	</section>
</template>

<script setup>
defineProps({ blok: Object });
</script>

<style lang="scss">
.skills__section {
	overflow-x: hidden;
	display: grid;
	grid-template-columns: 1fr 1fr 1fr;
	padding: 50px 0px 80px 0px;
	grid-row-gap: 60px;
	@media only screen and (max-width: $tablet) {
		grid-template-columns: 1fr 1fr;
	}
	@media only screen and (max-width: $mobile) {
		grid-template-columns: 1fr;
		justify-items: center;
		text-align: center;
	}
}

h2 {
	@include font-l;
}
</style>
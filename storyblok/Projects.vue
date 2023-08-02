<template>
	<section class="projects__section">
		<div class="projects__top">
			<h2>{{ blok.title }}</h2>
			<a href="#contact">
				<button>{{ blok.btn }}</button>
			</a>
		</div>
		<div class="projects__container" v-editable="blok">
			<StoryblokComponent
				v-for="blok in blok.columns"
				:key="blok._uid"
				:blok="blok"
			/>
		</div>
	</section>
</template>

<script setup>
defineProps({ blok: Object });
</script>

<style lang="scss" scoped>
.projects__section {
	padding-bottom: 100px;
}

.projects__top {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 80px;
	padding-top: 20px;
}

h2 {
	@include font-xl;
}

h3 {
	@include font-m;
	text-transform: uppercase;
	margin-bottom: 12px;
}

.projects__container {
	display: grid;
	grid-template-columns: repeat(auto-fill, minmax(450px, 1fr));
	gap: 20px;
	@media only screen and (max-width: $mobile) {
		grid-template-columns: 1fr;
		gap: 30px;
	}
}

.projects__item {
	cursor: pointer;
}

.project__item--img {
	height: 400px;
	background-position: center;
	background-size: cover;
	margin-bottom: 20px;
	position: relative;

	@media only screen and (max-width: $mobile) {
		height: 275px;
	}

	&:hover {
		.projects__overlay {
			opacity: 1;
			visibility: visible;
		}
	}

	.projects__overlay {
		visibility: hidden;
		opacity: 0;
		transition: opacity 500ms ease-in-out, visibility 500ms ease-in-out 0ms;
		position: absolute;
		width: 100%;
		height: 100%;
		background-color: #25252598;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		gap: 20px;
	}
}

.projects__item--skills {
	display: flex;
	gap: 10px;
	text-transform: uppercase;
}
</style>

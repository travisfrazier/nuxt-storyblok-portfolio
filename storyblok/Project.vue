<template>
	<div
		class="projects__item"
	>
		<div
			class="project__item--img"
			:style="{
				'background-image': 'url(' + `${blok.projectImg}` + ')',
			}"
		>
			<div class="projects__overlay">
				<a target="_blank" v-bind:href="blok.projectLive">
					<button>{{ blok.btnTextOne }}</button>
				</a>
				<a target="_blank" v-bind:href="projectCode">
					<button>{{ blok.btnTextTwo }}</button>
				</a>
			</div>
		</div>
		<h3>{{ blok.projectName }}</h3>
		<div class="projects__item--skills">
			<p>{{ blok.skillOne }}</p>
			<p>{{ blok.skillTwo }}</p>
			<p>{{ blok.skillThree }}</p>
		</div>
	</div>
</template>

<script setup>
defineProps({ blok: Object });
</script>


<style lang="scss" scoped>
h3 {
	@include font-m;
	text-transform: uppercase;
	margin-bottom: 12px;
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

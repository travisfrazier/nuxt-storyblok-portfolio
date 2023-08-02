<template>
	<div class="skill__item">
		<h2>{{ blok.title }}</h2>
		<p>{{ blok.text }}</p>
	</div>
</template>

<script setup>
defineProps({ blok: Object });
</script>
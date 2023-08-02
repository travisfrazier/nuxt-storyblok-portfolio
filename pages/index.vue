<script setup>
const story = await useAsyncStoryblok('home', { version: 'draft' })
</script>
 
<template>
    <div class="layout">
        <StoryblokComponent v-if="story" :blok="story.content" />
  </div>
</template>

<style lang="scss" scoped>
.layout {
	max-width: 1110px;
	margin: 0 auto;
	padding-left: 20px;
	padding-right: 20px;
}

.home-links a {
	margin-right: 1rem;
}

.skills__rings {
	position: absolute;
	right: -250px;
	top: 1050px;
	@media only screen and (max-width: $mobile) {
		right: -350px;
		top: 1450px;
	}
}

.header__rings {
	position: absolute;
	left: -150px;
	top: 120px;
	@media only screen and (max-width: $mobile) {
		left: -350px;
	}
}

.footer__rings {
	position: absolute;
	bottom: 190px;
	left: -150px;
	@media only screen and (max-width: $mobile) {
		left: -350px;
		bottom: 180px;
	}
}
</style>
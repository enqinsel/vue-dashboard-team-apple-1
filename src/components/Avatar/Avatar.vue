<script setup>
const props = defineProps(['image', 'size'])
</script>
	
<template>
	<div class="avatar">
		<img class="avatar__image" :src="image" :width="size" :height="size" />
	</div>
</template>
	
<style lang="scss">
.avatar {
	display: flex;
	justify-content: center;
	align-items: center;
	background-color: var(--color-text-light);
	border-radius: 50%;
	overflow: hidden;
}
</style>
<script setup lang="ts">
import TextEditor from '../components/TextEditor.vue'
</script>

<template>
	<article class="bg-white w-full h-full absolute top-0 left-0 text-black">
		<section class="mx-20 my-16 px-40 text-left">
			<TextEditor read-only />
		</section>
	</article>
</template>

<style scoped></style>

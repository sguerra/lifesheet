<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ msg: string }>()

const count = ref(0)
</script>

<template>
	<div class="h-96 justify-between flex flex-col">
		<h1 class="text-6xl flex-grow">{{ msg }}</h1>
		<section class="flex flex-col">
			<h2 class="text-2xl">Start here:</h2>
			<textarea rows="10" cols="100"></textarea>
		</section>
	</div>
</template>

<style scoped></style>

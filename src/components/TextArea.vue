<script setup lang="ts">
defineProps<{ label: string; placeholder: string; value: string }>()
</script>

<template>
	<section class="flex flex-col my-5">
		<h3 class="text-2xl font-bold my-5">{{ label }}</h3>
		<textarea
			rows="8"
			cols="90"
			class="bg-[#065471] text-lg font-bold focus:border-[#FFC045] border-4 resize-none p-5 outline-none"
			:placeholder="placeholder"
			:value="value"
		></textarea>
	</section>
</template>

<style scoped></style>

<script setup lang="ts">
defineProps<{ msg: string }>()
</script>

<template>
	<div class="justify-between flex flex-col">
		<div class="flex justify-center my-5">
			<div
				class="w-40 h-40 rounded-full bg-cover bg-[url('./public/leaf-shape.svg')]"
			></div>
		</div>
		<h1 class="text-6xl my-5">Lifesheet</h1>
		<h2 class="text-4xl my-5">
			<span class="text-[#0A91AB] brightness-125"> tu hoja de vida, </span
			><span class="text-[#FFC045] brightness-105">fácil</span>
		</h2>
		<section class="flex flex-col my-5">
			<h3 class="text-2xl font-bold my-5">Inicia aquí:</h3>
			<textarea
				rows="8"
				cols="90"
				class="bg-[#065471] text-lg font-bold focus:border-[#FFC045] border-4 resize-none p-5 outline-none"
			></textarea>
		</section>
	</div>
</template>

<style scoped></style>

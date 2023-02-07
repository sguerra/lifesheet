<script setup lang="ts">
defineProps<{ msg: string }>()
</script>

<template>
	<div class="flex flex-col h-full py-10">
		<video
			autoplay
			muted
			loop
			class="fixed -z-50 left-0 top-0 h-screen opacity-5"
		>
			<source src="../../public/typing-video.mp4" type="video/mp4" />
		</video>
		<div class="flex flex-col grow justify-between">
			<div class="justify-between flex flex-col">
				<div class="flex justify-center my-5">
					<div
						class="w-40 h-40 rounded-full bg-cover bg-[url('./public/leaf-shape.svg')]"
					></div>
				</div>
				<h1 class="text-6xl my-5">Lifesheet</h1>
				<h2 class="text-4xl my-5">
					<span class="text-[#0A91AB] brightness-125">
						tu hoja de vida </span
					><span class="text-[#FFC045] brightness-105">asistida</span>
				</h2>
			</div>

			<hr class="border-[#FFC045] border-2 brightness-125 mb-10" />

			<div class="justify-between flex my-2">
				<div class="flex flex-col">
					<div
						class="flex justify-center p-5 bg-[#065471] rounded-full shrink self-center"
					>
						<img
							src="../../public/cv-shape.svg"
							width="60"
							class="aspect-square"
						/>
					</div>
					<h3 class="my-5 text-2xl self-center">CV Editor</h3>
				</div>
				<div class="flex flex-col">
					<div
						class="flex justify-center p-5 bg-[#065471] rounded-full shrink self-center"
					>
						<img
							src="../../public/bot-shape.svg"
							width="60"
							class="aspect-square"
						/>
					</div>
					<h3 class="my-5 text-2xl self-center">Bot tips</h3>
				</div>
				<div class="flex flex-col">
					<div
						class="flex justify-center p-5 bg-[#065471] rounded-full shrink self-center"
					>
						<img
							src="../../public/ai-shape.svg"
							width="60"
							class="aspect-square"
						/>
					</div>
					<h3 class="my-5 text-2xl self-center">Typo highlight</h3>
				</div>
				<div class="flex flex-col">
					<div
						class="flex justify-center p-5 bg-[#065471] rounded-full shrink self-center"
					>
						<img
							src="../../public/pencil-shape.svg"
							width="60"
							class="aspect-square"
						/>
					</div>
					<h3 class="my-5 text-2xl self-center">Save on edit</h3>
				</div>
			</div>
			<div class="flex justify-center">
				<button
					class="bg-[#0A91AB]/50 text-white border-white border-4 hover:bg-[#FFC045] hover:text-[#065471] hover:border-[#065471] hover:brightness-110 w-96 py-3 px-5 text-2xl font-bold my-5"
					@click="$emit('onStart')"
				>
					Start
				</button>
			</div>
		</div>
	</div>
</template>

<style scoped></style>

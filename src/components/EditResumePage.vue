<script setup lang="ts">
defineProps<{ msg: string }>()
</script>

<template>
	<div>
		<div>
			<div class="fixed top-0 w-10/12 flex">
				<div class="flex mt-5 pr-10">
					<div
						class="w-9 h-9 rounded-full bg-cover bg-[url('./public/leaf-shape.svg')]"
					></div>
				</div>
				<h1 class="text-2xl mt-5 pr-20">Lifesheet</h1>
				<h2 class="text-xl mt-5">
					<span class="text-[#0A91AB] brightness-125">
						tu hoja de vida, </span
					><span class="text-[#FFC045] brightness-105">fácil</span>
				</h2>

				<button
					class="absolute right-48 top-1 bg-[#0A91AB]/50 text-white border-white border hover:bg-[#FFC045] hover:text-[#065471] hover:border-[#065471] w-50 py-1 px-10 text-md font-bold mt-4"
					@click="$emit('onBack')"
				>
					Go Back
				</button>
				<button
					class="absolute right-0 top-1 bg-[#FFC045] text-[#065471] border-white border hover:bg-[#0A91AB]/50 hover:text-white hover:brightness-110 w-50 py-1 px-10 text-md font-bold mt-4"
					@click="$emit('onView')"
				>
					Preview
				</button>
			</div>

			<div class="justify-between flex my-5">
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
					<h3 class="my-5 text-2xl self-center">Typo finder</h3>
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
		</div>
	</div>
</template>

<style scoped></style>

<script setup lang="ts">
import BoxPanel from '../components/BoxPanel.vue'
import TextEditor from '../components/TextEditor.vue'
import BotTips from '../components/BotTips.vue'

defineProps<{ msg: string }>()
</script>

<template>
	<div class="flex flex-col h-full relative">
		<div class="fixed top-0 left-10 right-10 flex">
			<div class="flex mt-4 pr-5">
				<div
					class="w-9 h-9 rounded-full bg-cover bg-[url('./public/leaf-shape.svg')]"
				></div>
			</div>
			<h1 class="text-2xl mt-5 pr-20">Lifesheet</h1>
			<h2 class="text-xl mt-6">
				<span class="text-[#0A91AB] brightness-125">
					tu hoja de vida </span
				><span class="text-[#FFC045] brightness-105">asistida</span>
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
		<div class="flex grow mt-24 h-5/6">
			<div class="grow h-full m-0 p-0 max-h-">
				<BoxPanel
					title="CV Editor"
					img="../../public/cv-shape.svg"
					class-name="grow flex flex-col h-5/6"
				>
					<TextEditor />
				</BoxPanel>
			</div>
			<div class="grow px-5 flex flex-col w-96 h-full">
				<BoxPanel
					title="Bot tips"
					img="../../public/bot-shape.svg"
					class-name="flex flex-col h-5/6"
				>
					<BotTips />
				</BoxPanel>
			</div>
		</div>
	</div>
</template>

<style scoped></style>

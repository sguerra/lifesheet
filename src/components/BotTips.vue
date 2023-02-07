<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
type Tip = {
	section: string
	text: string
}

const tips = ref<Tip[]>([])
const errorId = ref<number>(0)
const sections = [
	'contact',
	'role',
	'work experience',
	'skills',
	'education',
	'languages',
]
const loading = ref<boolean>(false)
const interval = ref<number>(null)
const DEFAULT_INTERVAL = 30000

async function getTip() {
	loading.value = true

	sections.push(sections.shift())
	const section = sections.at(0)

	const result = await fetch('https://api.cohere.ai/generate', {
		method: 'POST',
		headers: {
			Authorization: `BEARER ${import.meta.env.VITE_COHERE_API_KEY}`,
			'Cohere-Version': '2022-12-06',
			Accept: '*/*',
			'Content-Type': 'application/json; charset=utf-8',
		},
		body: `{
                "model": "command-medium-nightly",
                "prompt": "Give me a tip on ${section} section of a resume",
                "max_tokens": 332,
                "temperature": 0.9,
                "k": 0,
                "p": 0.75,
                "frequency_penalty": 0,
                "presence_penalty": 0,
                "stop_sequences": [${'\n'}],
                "return_likelihoods": "NONE"
            }`,
	})

	const { generations } = await result.json()

	if (generations && generations.length) {
		tips.value.push({ section: section, ...generations.at(0) })
		interval.value = setTimeout(getTip, DEFAULT_INTERVAL)
	} else {
		tips.value.push({
			id: errorId.value,
			section: 'error',
			text: 'Error while connecting with co:here API',
		})
		errorId.value = errorId.value++
	}
	loading.value = false
}

onMounted(async () => {
	getTip()
})

onUnmounted(() => {
	if (interval.value) {
		clearTimeout(interval.value)
	}
})
</script>

<template>
	<div class="w-full h-full overflow-x-clip overflow-y-auto">
		<div class="block m-3" v-for="tip in tips" :key="tip.id">
			<div
				v-if="tip.section == 'error'"
				class="bg-[#FFC045]/50 color-[#0C2233] text-justify p-3"
			>
				{{ tip.text }}
			</div>
			<div v-else class="bg-[#0A91AB]/50 color-white text-justify p-3">
				{{ tip.text }}
			</div>
		</div>
		<div class="flex align-middle justify-center" v-if="loading">
			<img src="../../public/loading-animation.svg" />
		</div>
	</div>
</template>

<style scoped></style>

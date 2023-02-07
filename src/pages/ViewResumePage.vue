<script setup lang="ts">
import { onMounted } from 'vue'
import TextEditor from '../components/TextEditor.vue'

function onPrint() {
	window.print()
}

onMounted(() => {
	const $container = document.querySelector('.ql-snow')

	if ($container) {
		$container.className = $container.className.replace('ql-snow', '')
	}
})
</script>

<template>
	<article class="bg-white w-full h-full absolute top-0 left-0 text-black">
		<div class="fixed top-0 left-10 right-10 flex">
			<button
				class="absolute right-48 top-1 bg-[#0A91AB]/75 text-white border-white border hover:bg-[#FFC045] hover:text-[#065471] hover:border-[#065471] w-50 py-1 px-10 text-md font-bold mt-4"
				@click="$emit('onBack')"
			>
				Go Back
			</button>
			<button
				class="absolute right-0 top-1 bg-[#FFC045]/75 text-[#065471] border-white border hover:bg-[#0A91AB]/50 hover:text-white hover:brightness-110 w-50 py-1 px-10 text-md font-bold mt-4"
				@click="onPrint"
			>
				Print
			</button>
		</div>
		<section class="mx-20 my-16 px-40 text-left">
			<TextEditor read-only />
		</section>
	</article>
</template>

<style scoped>
@media print {
	button {
		display: none !important;
	}
}
</style>

<script setup lang="ts">
defineProps<{ title: string; img: string; className: string }>()
</script>

<template>
	<div :class="className">
		<div class="flex flex-col">
			<div class="flex bg-[#065471]">
				<div
					class="flex justify-center p-5 rounded-full shrink self-center"
				>
					<img :src="img" width="26" class="aspect-square" />
				</div>
				<h3 class="my-2 text-xl self-center">
					{{ title }}
				</h3>
			</div>
		</div>
		<div class="h-full grow bg-[#0A91AB]/10">
			<slot></slot>
		</div>
	</div>
</template>

<style scoped></style>

<script setup lang="ts">
import { ref } from 'vue'
import LandingPage from './components/LandingPage.vue'
import EditResumePage from './components/EditResumePage.vue'
import ViewResumePage from './components/ViewResumePage.vue'

function getModeFromURL() {
	const url = new URL(window.location.href)
	const modeValue = url.searchParams.get('mode')
	return modeValue || 'home'
}
function setModeInURL(modeValue: string) {
	mode.value = modeValue

	const url = new URL(window.location.href)
	url.searchParams.set('mode', modeValue)
	window.history.pushState({}, null, `${url.origin}${url.search}`)
}

const mode = ref<'home' | 'edit' | 'view'>(getModeFromURL())

window.addEventListener('popstate', () => {
	mode.value = getModeFromURL()
})

function onStart() {
	setModeInURL('edit')
}
function onBack() {
	window.history.back()
}
function onView() {
	setModeInURL('view')
}
</script>

<template>
	<div v-if="mode === 'home'">
		<LandingPage msg="Lifesheet" @onStart="onStart" />
	</div>
	<div v-if="mode === 'edit'">
		<EditResumePage msg="Lifesheet" @onBack="onBack" @onView="onView" />
	</div>
	<div v-if="mode === 'view'">
		<ViewResumePage />
	</div>
</template>

<style scoped></style>

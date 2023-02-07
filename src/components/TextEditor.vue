<script setup lang="ts">
import { onMounted } from 'vue'
import Quill from 'quill'

const props = defineProps<{ readOnly?: boolean }>()
const readOnly = props.readOnly ?? false

function getContentsFromURL() {
	const url = new URL(window.location.href)
	const contentsValue = url.searchParams.get('contents')
	return contentsValue || null
}
function setContentsInURL(contentsValue: string) {
	const url = new URL(window.location.href)
	url.searchParams.set('contents', contentsValue)
	window.history.replaceState({}, null, `${url.origin}${url.search}`)
}

onMounted(() => {
	const toolbarOptions = [
		['bold', 'italic', 'underline', 'strike'], // toggled buttons
		[{ list: 'ordered' }, { list: 'bullet' }],
		[{ header: [1, 2, 3, 4, 5, 6, false] }],
		[{ font: [] }],
		[{ align: [] }],
		['clean'], // remove formatting button
	]

	const editor = new Quill('#editor', {
		modules: {
			toolbar: toolbarOptions,
		},
		theme: readOnly ? 'bubble' : 'snow',
		readOnly: readOnly,
	})

	//
	const contents = getContentsFromURL()
	if (contents) {
		editor.setContents(JSON.parse(atob(contents)))
	}

	// listen to changes
	editor.on('text-change', (delta, oldDelta, source) => {
		if (source === 'user') {
			setContentsInURL(btoa(JSON.stringify(editor.getContents())))
		}
	})

	// focus on editor
	editor.focus()
})
</script>

<template>
	<div class="h-full w-full text-black bg-white pb-11">
		<!-- Create the editor container -->
		<div id="editor">
			<p class="ql-align-center">
				email@example.com · (52) 123 45 67 89 ·
				<a href="yourwebsite.dev">yourwebsite.dev</a> ·
				<a href="https://linkedin.com/in/your-linkedin-profile/"
					>/in/your-linkedin-profile/</a
				>
				·
				<a href="https://github.com/your-github-profile"
					>github.com/your-github-profile</a
				>
			</p>

			<br /><br />

			<h1>FULL NAME</h1>

			<br />

			<h2>ROLE</h2>
			Short description up to 4 lines

			<br /><br />

			<h2>WORK EXPERIENCE</h2>
			<br />
			<h3>YOUR ROLE at COMPANY NAME</h3>
			<h4>RESPONSIBILITIES</h4>
			<ul>
				<li>Responsibility 1</li>
				<li>Responsibility 2</li>
			</ul>

			<h4>ACCOMPLISHMENTS</h4>
			<ul>
				<li>Accomplishment 1</li>
				<li>Accomplishment 2</li>
			</ul>

			<br />

			<h2>SKILLS</h2>
			<ul>
				<li>Skill 1</li>
				<li>Skill 2</li>
				<li>Skill 3</li>
			</ul>

			<br />

			<h2>EDUCATION</h2>
			<h3>Education Title, University</h3>
			MONTH YEAR - MONTH YEAR [City, Country]

			<br /><br />

			<h2>LANGUAGES</h2>
			<p>English, Spanish</p>
		</div>
	</div>
</template>

<style scoped></style>

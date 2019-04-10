<template>
	<div>
		<h1 class="type_project_title">{{title}}</h1>
		<h2 class="type_project_date">{{display_date}}</h2>
		<p class="type_paragraph">{{description}}</p>
	</div>
</template>

<script>
export default {
	name: 'Project',
	props: {
		title: String,
		display_date: String,
		description: String,
		images: Array
	}
}
</script>

<style>
</style>
<template>
	<div id="app" class="wrapper">
		<h1 class="type_title">Arjo Nagelhout</h1>
		<h2 class="type_subtitle">This is a subtitle that explains what I do.</h2>
		<p class="type_paragraph">Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio </p>
		<h1 class="type_page_title">My portfolio:</h1>
		<ProjectsContainer/>
	</div>
</template>

<script>
import ProjectsContainer from './components/ProjectsContainer.vue'

export default {
	name: 'app',
	components: {
		ProjectsContainer
	}
}
</script>

<style>
</style>

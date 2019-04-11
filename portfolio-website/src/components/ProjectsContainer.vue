<template>
	<div id="projects_container">
		<Project 
			v-for="project in projects" 
			v-bind:title="project.title"
			v-bind:display_date="project.display_date"
			v-bind:description="project.description"
			v-bind:images="project.images"

			v-bind:key="project.title"
		/>
	</div>
</template>

<script>
import Project from './Project.vue'

export default {
	name: 'ProjectsContainer',
	data: function () {
		return {
			projects: []
		}
	},
	created: function() {
		fetch(process.env.BASE_URL+"projects.json")
			.then(r => r.json())
			.then(json => {
				this.projects = this.interpret_projects(json.projects);
			});
	},
	methods: {
		interpret_projects: function(projects_in) {

			var projects_out = projects_in;

			function convert_date(date_string) {
				var date = new Date(date_string);
				var date_options = {month: 'long', year: 'numeric'};
				return date.toLocaleDateString("en-US", date_options);
			}
			
			// Add rendering information to project
			projects_out.map(function callback(project) {

				// Set display date
				if ('single' in project.time) {
					project.display_date = convert_date(project.time.single);
				} else {
					project.display_date = convert_date(project.time.start) + " - " + convert_date(project.time.end);
				}
			});

			return projects_out;
		}
	},
	components: {
		Project
	}
}
</script>

<style lang="scss" scoped>

</style>
<template>
	<div id="app" class="wrapper">
		<h1 class="type_title">Arjo Nagelhout</h1>
		<h2 class="type_subtitle">This is a subtitle that explains what I do.</h2>
		<p class="type_paragraph">Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio </p>
		<h1 class="type_page_title">My portfolio:</h1>
		<Project 
			v-for="project in interpreted_projects" 
			v-bind:title="project.title"
			v-bind:display_date="project.display_date"
			v-bind:description="project.description"
			v-bind:key="project.title"
		/>
	</div>
</template>

<script>
import Project from './components/Project.vue'

export default {
	name: 'app',
	data: function () {
		return {
			projects: [
				{
					title: "You're being followed",
					time: {
						start: new Date("2019/02/01"),
						end: new Date("2020/03/01")
					},
					description: "Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio"
				},
				{
					title: "Strange Worlds",
					time: {
						single: new Date("2018/01/01")
					},
					description: "Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio"
				},
				{
					title: "Double Lasers",
					time: {
						start: new Date("2015/11/01"),
						end: new Date("2017/01/01")
					},
					description: "Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio"
					
				}
			]
		}
	},
	computed: {
		interpreted_projects: function() {

			var projects_out = this.projects.slice();

			function convert_date(date) {
				var date_options = {month: 'long', year: 'numeric'};

				return date.toLocaleDateString("en-US", date_options);
			}
			
			projects_out.map(function callback(project) {
				
				if ('single' in project.time) {
					project.display_date = convert_date(project.time.single);
				} else {
					project.display_date = convert_date(project.time.start) + " - " + convert_date(project.time.end);
				}

				project.changed = true;
			});

			return projects_out;

		}
	},
	components: {
		Project
	}
}
</script>

<style>
</style>

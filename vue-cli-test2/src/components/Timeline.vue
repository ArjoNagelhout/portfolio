<template>
	<div id="timeline_container">
		<div id="projects_container">
			<div class="project_container" v-for="project in projects" :key="project.id">
				<h1 class="project_title">{{project.title}}</h1>
				<h2 class="project_subtitle">{{project.subtitle}}</h2>
				<div class="project_content">
					<div v-for="content_element in project.content" :key="content_element.id">
						<p v-if="content_element.type==='text'">{{content_element.text}}</p>
					</div>
				</div>
			</div>
		</div>
		<div id="middle_container">
		</div>
		<div id="places_container">
		</div>
	</div>
</template>

<script>
export default {
	name: 'Timeline',
	data: function() {
		return {
			projects: [
				{
					title: "You're being followed",
					subtitle: "An augmented reality puzzle about the state of internet privacy",
					period: {
						start: "",
						end: ""
					},
					importance: 0,
					content: [
						{
							type: "text",
							text: "Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi."
						},
						{
							type: "text",
							text: "Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi."
						}
					]
				}
			],
			places: [
				{
					name: "VWO N&T",
					description: "At Gymnasium Novum in the Netherlands. ",
					period: {
						start: "",
						end: ""
					}
				}
			]
		}
	},
	methods: {
	},
	props: {
		
	}
}
</script>

<style scoped>
</style>

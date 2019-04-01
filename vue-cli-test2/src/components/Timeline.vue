<template>
	<div id="timeline_container">
		<div id="dates_container">
		</div>
		<div id="places_container">
		</div>
		<div id="projects_container">
			<div class="project_container" v-for="project in projects" :key="project.id" v-bind:style="{ top: project.top + 'px' }">
				<h1 class="project_title">{{project.title}}</h1>
				<h2 class="project_subtitle">{{project.subtitle}}</h2>
				<div class="project_content">
					<div v-for="content_element in project.content" :key="content_element.id">
						<p v-if="content_element.type==='text'">{{content_element.text}}</p>
					</div>
				</div>
			</div>
		</div>
		
	</div>
</template>

<script>
export default {
	name: 'Timeline',
	data: function() {
		return {
			timeline: {
				height: 0
			},
			projects: [
				{
					title: "You're being followed",
					subtitle: "An augmented reality puzzle about the state of internet privacy",
					period: {
						start: new Date("2019/02/04"),
						end: new Date("2019/03/29")
					},
					importance: 0,
					place: "hku",
					top: 0,
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
	created: function() {
		this.render_timeline();
	},
	methods: {
		render_timeline() {
			for (var i=0; i<this.projects.length; i++) {
				var project = this.projects[i];
				project.top = 30;
			}
		},
		compare_start_dates(a, b) {
			if (a.period.start < b.period.start)
				return -1;
			if (a.period.start > b.period.start)
				return 1;
			return 0;
		},
		compare_end_dates(a, b) {
			if (a.period.end < b.period.end)
				return -1;
			if (a.period.end > b.period.end)
				return 1;
			return 0;
		},
		generate_timeline() {
			// Generate the timeline div that shows the dates
			var min = this.projects.sort(c)
		}
	},
	props: {
		
	}
}
</script>

<style scoped>

#timeline_container {
	display:grid;
	grid-template-columns:200px 50px auto;
}

#projects_container {
	position:relative;
}

#dates_container {
	background-color:gray;
}

.project_container {
	position:absolute;
	background-color:gainsboro;
}


</style>

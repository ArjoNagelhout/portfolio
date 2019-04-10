<template>
	<div class="project_container">
		<div class="project_text">
			<h1 class="type_project_title">{{title}}</h1>
			<div class="project_info">
				<div class="date_container">
					<h2 class="type_project_date">{{display_date}}</h2>
				</div>
				<p class="type_paragraph project_description">{{description}}</p>
			</div>
		</div>
		<img v-for="image in images" v-bind:src="image_path(image)"/>
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
	},
	methods: {
		image_path: function(path) {
			return process.env.BASE_URL+path;
		}
	}
}
</script>

<style lang="scss" scoped>

.project_container {
	width:100%;
	height:140px;
}

.project_text {
	width:400px;
}

.project_info {

	display:flex;
	flex-direction:row;
}

.project_description {

}

.date_container {
	width:80px;
	flex-shrink:0;
	flex-grow:0;

	h2 {
		transform: rotate(-90deg);
	}
}

img {
	height:100%;
	background-color:gray;
}

</style>
<template>
	<div id="information_container">
		<div id="photo_container">
			<!--<img src="./../assets/photo.jpg">-->
		</div>
		<div id="about_container">
			<h1>Arjo Nagelhout</h1>
			<p>I am a designer. </p>
		</div>
		<div id="navigation_container">
			<div class="navigation_element" v-for="navigation_element in navigation_elements" :key="navigation_element.id">
			
				<a v-bind:href="navigation_element.url" :target="get_target(navigation_element)">{{navigation_element.text}} →</a>

			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'InformationCard',
	data: function() {
		return {
			navigation_elements: [
				{
					text: "Send me an email",
					url: "mailto:arjo.nagelhout@gmail.com",
					open_in_new_tab: false

				},
				{
					text: "GitHub",
					url: "https://www.github.com/ArjoNagelhout",
					open_in_new_tab: true
				},
				{
					text: "YouTube",
					url: "https://www.youtube.com/channel/UCRK8NToksymdD7sqNj1gbcQ",
					open_in_new_tab: true
				}
			]
		}
	},
	methods: {
		get_target(navigation_element) {
			return (navigation_element.open_in_new_tab ? "_blank" : "_self")
		}
	},
	props: {
		
	}
}
</script>

<style scoped>

#information_container {
	display:grid;
	grid-template-columns: 200px auto 200px;
	max-width:800px;
	margin:auto;
}

img {
	max-width:100%;
}

</style>

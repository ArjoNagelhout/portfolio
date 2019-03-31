<template>
	<div id="information_container">
		<div id="photo_container">
			<img src="./../assets/photo.jpg">
		</div>
		<div id="about_container">
			<h1>Arjo Nagelhout</h1>
			<p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.</p>
		</div>
		<div id="navigation_container">
			<div v-for="navigation_element in navigation_elements" :key="navigation_element.id">
			
				<a v-bind:href="navigation_element.url" target="_blank">{{navigation_element.name}} →</a>

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
					name: "GitHub",
					url: "https://www.github.com/ArjoNagelhout"
				},
				{
					name: "YouTube",
					url: "https://www.youtube.com/channel/UCRK8NToksymdD7sqNj1gbcQ"
				}
			]
		}
	},
	props: {
		
	}
}
</script>

<style scoped>

</style>

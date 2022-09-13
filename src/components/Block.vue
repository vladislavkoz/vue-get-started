<template>
	<div class="container">
		<div class="header">
			<slot name="header">
				<span>Header</span>
			</slot>
		</div>
		<div class="body">
			<slot name="body">
				<span>Body</span>
			</slot>
		</div>
		<div class="footer">
			<slot name="footer">
				<span>Footer</span>
			</slot>
		</div>
	</div>
</template>

<script>
export default {
	name: 'AppBlock',
	props: {
	
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container {
	display: flex;
	flex-direction: column;
	border: 1px solid black;
	
	div {
		padding: 1rem;
		min-height: 10rem;
		min-width: 10rem;
	}
	
	.header {
		background-color: rgba(0, 255, 252, 0.11);
	}
	
	.body {
		background-color: rgba(167, 246, 115, 0.16);
	}
	
	.footer {
		background-color: rgba(252, 0, 255, 0.15);
	}
}
</style>

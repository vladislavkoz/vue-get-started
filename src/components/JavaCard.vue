<template>
	<app-card :card="card">
		<template #icon>
			<img class="icon" src="@/assets/java.png"/>
		</template>
		<template #title>
			<div class="face face2">
				<h2>Java</h2> <br>
				<h2>language</h2>
			</div>
		</template>
	</app-card>
</template>

<script>
import AppCard from "@/components/Card";

export default {
	name: 'AppJavaCard',
	components: {AppCard},
	props: {
		card: Object,
	}
}
</script>

<style scoped lang="scss">
.card .face.face2 {
	background-color: #a7f673;
	border-radius: 15px;
}


.card:hover .face.face2 {
	height: 100px;
	top: 0;
	
	h2 {
		font-size: 1.5em;
	}
}

.face {
	position: absolute;
	left: 0;
	width: 100%;
	height: 100%;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	
	&.face2 {
		transition: 0.5s;
		
		h2 {
			margin: 0;
			padding: 0;
			font-size: 4em;
			color: #fff;
			transition: 0.5s;
			z-index: 10;
			text-shadow: -1px 0 black, 0 1px black, 1px 0 black, 0 -1px black;
		}
	}
}

.icon {
	height: 4rem;
	width: 4rem;
}
</style>

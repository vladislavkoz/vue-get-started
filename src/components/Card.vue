<template>
	<div class="card">
		<slot class="card-content">
			<div class="face face1">
				<slot name="face1-header"></slot>
				<div class="content">
					<slot name="content">
						<slot name="icon"></slot>
						<h2 :class="`text ${card.classname}`">{{ card.title }}</h2>
						<p :class="`text ${card.classname}`">
							{{card.text}}
						</p>
					</slot>
				</div>
			</div>
			<slot name="title">
				<div class="face face2">
					<h2>{{ card.title }}</h2>
				</div>
			</slot>
		</slot>
  </div>
</template>

<script>
export default {
	name: 'AppCard',
	props: {
		card: Object,
		index: Number,
		text: {
			type: String,
			default: '',
		},
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card {
	position: relative;
	width: 300px;
	height: 400px;
	margin: 1rem 10rem;
	background: #000;
	border-radius: 15px;
	box-shadow: 0 15px 60px rgba(0, 0, 0, 0.5);
	
	.face {
		position: absolute;
		bottom: 0;
		left: 0;
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		
		&.face1 {
			box-sizing: border-box;
			display: flex;
			flex-direction: column;
			padding: 20px;
			
			h2 {
				margin: 0;
				padding: 0;
			}
			
			.text {
				color: white;
			}
			
			.react {
				background-color: #00fffc;
				-webkit-background-clip: text;
				-webkit-text-fill-color: transparent;
			}
			
			.angular {
				background-color: #fffc00;
				-webkit-background-clip: text;
				-webkit-text-fill-color: transparent;
			}
			
			.vue {
				background-color: #fc00ff;
				-webkit-background-clip: text;
				-webkit-text-fill-color: transparent;
			}
		}
		
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
}

.card:hover .face.face2 {
	height: 60px;
	
	h2 {
		font-size: 2em;
	}
}

.card .face.face2 {
	background-image: linear-gradient(
			40deg,
			#a7f673 0%,
			#ff379a 45%,
			#28a3f6 100%
	);
	border-radius: 15px;
}

.card:nth-child(1) .face.face2 {
	background-image: linear-gradient(
			40deg,
			#fffc00 0%,
			#fc00ff 45%,
			#00fffc 100%
	);
	border-radius: 15px;
}

.card:nth-child(2) .face.face2 {
	background-image: linear-gradient(
			40deg,
			#fc00ff 0%,
			#00fffc 45%,
			#fffc00 100%
	);
	border-radius: 15px;
}

.card:nth-child(3) .face.face2 {
	background-image: linear-gradient(
			40deg,
			#00fffc 0%,
			#fc00ff 45%,
			#fffc00 100%
	);
	border-radius: 15px;
}
</style>

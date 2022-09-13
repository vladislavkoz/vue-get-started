<template>
	<div class="about">
		<div class="example-1">
			<app-block>
				<template #header>
					Custom header
				</template>
				
				<template #body>
					Custom header
				</template>
			</app-block>
		</div>
		<div class="cards" v-if="false">
			<app-framework-card
				v-for="(card, index) in cards"
				:card="card"
				:index="index"
				:key="index"
				:on-delete="onDelete"
				@duplicate="onDuplicate"
			/>
		</div>
		
		<div class="cards" v-if="false">
			<app-java-card :card="javaCard"/>
			<app-python-card :card="pythonCard"/>
		</div>
	</div>
</template>
<script>
import AppFrameworkCard from "@/components/FrameworkCard";
import AppJavaCard from "@/components/JavaCard";
import AppPythonCard from "@/components/PythonCard";
import AppBlock from "@/components/Block";

export default {
	name: 'HelloWorld',
	components: {AppBlock, AppPythonCard, AppJavaCard, AppFrameworkCard},
	data() {
		return {
			cards: [
				{
					title: 'Angular',
					classname: 'angular',
					text: 'Angular is a TypeScript-based free and open-source web application framework'
				},
				{
					title: 'React',
					classname: 'react',
					text: 'React is a free and open-source front-end JavaScript library'
				},
				{title: 'VueJs', classname: 'vue', text: 'Vue is a progressive JavaScript framework'},
			],
			javaCard: {
				title: 'Java', classname: '', text: 'Java is a class-based, object-oriented programming language'
			},
			pythonCard: {
				title: 'Python', classname: '', text: 'Python is a high-level, general-purpose programming language'
			}
		}
	},
	methods: {
		onDelete(cardIndex) {
			this.cards.splice(cardIndex, 1);
		},
		onDuplicate(cardIndex) {
			if (cardIndex !== undefined) {
				const card = this.cards[cardIndex];
				this.cards = [...this.cards.slice(0, cardIndex + 1), {...card}, ...this.cards.slice(cardIndex + 1, this.cards.length)]
			}
		}
	}
}
</script>
<style scoped lang="scss">
.example-1 {
	margin-bottom: 2rem;
}

.cards {
	display: flex;
	margin-bottom: 2rem;
	justify-content: center;
	flex-wrap: wrap;
}
</style>
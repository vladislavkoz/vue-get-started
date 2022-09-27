<template>
	<div class="about">
		<div class="example-0">
      <app-block/>
      <hr class="dashed">
    </div>


    <div class="example-1" v-if=-false>
			<app-block>
				<template #header>
					Custom header
				</template>

				<template #body>
					Custom body
				</template>
			</app-block>
		</div>
    <hr class="dashed">


    <div class="example-2" v-if=false>
      <app-block>
        <template #header>
          Custom header
        </template>

        <template #body>
          <p>Some body with HTML</p>
          <button>Hey I'm button</button>
        </template>
      </app-block>
    </div>
    <hr class="dashed">


    <div class="cards" v-if="false">
      <app-card
        v-for="(card, index) in cards"
        :key="index"
        :card="card"
        :index="index"
      />
    </div>
    <hr class="dashed">


    <div class="cards" v-if="false">
			<app-framework-card
				v-for="(card, index) in cards"
        :key="index"
        :card="card"
        :index="index"
				:on-delete="onDelete"
				@duplicate="onDuplicate"
			/>
		</div>
    <hr class="dashed">


		<div class="cards" v-if="false">
			<app-java-card :card="javaCard"/>
			<app-python-card :card="pythonCard"/>
		</div>
    <hr class="dashed">
	</div>
</template>
<script>
import AppFrameworkCard from "@/components/FrameworkCard";
import AppCard from "@/components/Card";
import AppJavaCard from "@/components/JavaCard";
import AppPythonCard from "@/components/PythonCard";
import AppBlock from "@/components/Block";
import ComponentExample from "@/components/ComponentExample";

export default {
	name: 'HelloWorld',
	components: {AppBlock, AppPythonCard, AppJavaCard, AppFrameworkCard, AppCard},
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
		},
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

hr.dashed {
  border-top: 3px dashed #bbb;
}
</style>
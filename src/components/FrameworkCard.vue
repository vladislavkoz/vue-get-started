<template>
	<app-card :card="card" :index="index">
		<template #face1-header>
			<button class="remove-button" @click="onDelete(index)">Remove</button>
			<button @click="$emit('duplicate', index)">
				Duplicate
			</button>
		</template>
	</app-card>
</template>

<script>
import AppCard from "@/components/Card";

export default {
	name: 'AppFrameworkCard',
	components: {AppCard},
	props: {
		card: Object,
		index: Number,
		onDelete: Function,
	}
}
</script>

<style scoped lang="scss">
	.remove-button {
		background-color: #d50000;
	}
</style>

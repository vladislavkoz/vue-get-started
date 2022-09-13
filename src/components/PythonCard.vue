<template>
	<app-card :card="card" class="card">
		<template #icon>
			<img class="icon" src="@/assets/python.png"/>
		</template>
	</app-card>
</template>

<script>
import AppCard from "@/components/Card";

export default {
	name: 'AppPythonCard',
	components: {AppCard},
	props: {
		card: Object,
	}
}
</script>

<style scoped lang="scss">
.icon {
	height: 5rem;
	width: 5rem;
}
</style>

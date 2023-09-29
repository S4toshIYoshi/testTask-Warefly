<template>
	<div class="projects">
		<client-only>
			<Project v-for="(item, index) in projects" :project="item" :key="index" />
		</client-only>
	</div>
</template>

<script>
import Project from '@/src/components/Project.vue';

export default {
	components: {
		Project,
	},
	data() {
		return {
			projects: [],
		};
	},

	mounted() {
		this.getRepos();
	},

	methods: {
		async getRepos() {
			const projects = await fetch(
				'https://api.github.com/users/S4toshIYoshi/repos'
			);
			const data = await projects.json();
			this.projects = data;
		},
	},
};
</script>

<style>
.projects {
	width: 90%;
	margin: 30px auto;

	display: flex;
	flex-direction: column;
	align-items: center;
	row-gap: 30px;
}
</style>

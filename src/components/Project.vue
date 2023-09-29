<template>
	<div class="card-projects">
		<a :href="project.svn_url" class="name">{{ project.name }}</a>
		<div class="languages">
			<client-only>
				<div class="language" v-for="(item, index) in languages" :key="index">
					{{ index }}
				</div>
			</client-only>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		project: {
			type: Object,
		},
	},

	data() {
		return {
			languages: [],
		};
	},

	mounted() {
		this.getLanguage();
	},

	methods: {
		async getLanguage() {
			const data = await fetch(this.project.languages_url);
			this.languages = await data.json();
		},
	},
};
</script>

<style>
.card-projects {
	min-width: 100%;
	border-radius: 20px;
	padding: 24px;

	box-shadow: 2px 2px 10px 1px rgba(0, 0, 0, 0.2);
}

.name {
	color: #0969da;
	font-size: 20px;
}

.languages {
	width: 100%;

	margin-top: 15px;

	display: flex;
	flex-flow: row wrap;
	column-gap: 10px;

	color: #656d76;

	font-size: 15px;
}
</style>

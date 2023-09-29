<template>
	<div>2</div>
</template>

<script>
export default {
	data() {
		return {
			likes: 0,
		};
	},

	methods: {
		addLike() {
			this.likes++;
		},

		removeLike() {
			this.likes--;
		},
	},
};
</script>

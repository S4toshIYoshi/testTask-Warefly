<template>
	<div class="layout">
		<div class="header">
			<h2 class="title">Kroshechkin</h2>
			<h3 class="description">My projects</h3>
		</div>
		<slot />
	</div>
</template>

<script>
export default {};
</script>

<style>
.layout {
	min-height: 100vh;
}

.header {
	margin-top: 30px;
	width: 100%;

	display: flex;
	flex-direction: column;
	align-items: center;
}

.title {
	font-size: 30px;
	color: #0969da;
}

.description {
	font-size: 20px;
	color: #656d76;
}
</style>

<template>
	<header class="header">
		<h1>Kombinator</h1>
	</header>
</template>

<script>
export default {
	name: 'Header'
}
</script>

<style lang="stylus" scoped>
.header
	text-align center
	padding 1rem 1rem 2rem

h1
	margin 0
	font 300 6rem/1 var(--font-stack-heading)

	@media (max-width 1024px)
		font-size 4rem
</style>

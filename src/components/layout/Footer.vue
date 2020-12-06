<template>
	<footer class="footer">
		<p>© {{ year }} Kombinator - <a href="https://github.com/EmmanuelBeziat/kombinator/issues">Report a bug 🐞</a></p>
		Made with ❤ by <a href="https://www.emmanuelbeziat.com/">Emmanuel Béziat</a>
	</footer>
</template>

<script>
export default {
	name: 'Footer',

	computed: {
		year: () => Intl.DateTimeFormat(navigator.language, { year: 'numeric' }).format(new Date())
	}
}
</script>

<style lang="stylus" scoped>
.footer
	padding 2rem 1rem 1rem
	text-align center

	p
		margin 0
</style>

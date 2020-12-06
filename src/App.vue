<template>
	<Header />

	<main class="main">
		<router-view />
	</main>

	<Footer />
</template>

<script>
import Header from '@/components/layout/Header'
import Footer from '@/components/layout/Footer'

export default {
	components: {
		Header,
		Footer
	}
}
</script>

<style lang="stylus">
@require '~@/assets/fonts/mathlete/mathlete.css'

:root
	--color-background #1f2533
	--color-text #fff
	--color-primary #ffb655
	--color-alt #ee8700

	--font-stack-common "Segoe UI", "Helvetica Neue", Roboto, Helvetica, Arial, sans-serif
	--font-stack-heading Mathlete, var(--font-stack-common)

*
*::before
*::after
	box-sizing inherit

html
	box-sizing border-box
	overflow-y scroll
	scroll-behavior smooth

	@media (prefers-reduced-motion reduce)
		scroll-behavior auto

body
	margin 0
	font 400 16px/1.5 var(--font-stack-common)
	background var(--color-background)
	color var(--color-text)

a
	text-decoration none
	transition .25s ease-in-out
	color var(--color-primary)

	&:hover
	&:focus
		text-decoration underline
		color var(--color-alt)

#app
	min-height 100vh

	@media (max-width 1024px)
		display grid
		grid-template-rows auto 1fr auto
</style>

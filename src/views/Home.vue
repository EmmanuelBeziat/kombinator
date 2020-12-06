<template>
	<div class="home">
		<InputNumber @on-change="number => result = number" />

		<div class="result" v-if="result">
			<span class="number">{{ Intl.NumberFormat('en-US').format(result)}}</span>

			<span v-if="result < 2">possible combination</span>
			<span v-else>possible combinations</span>
			<span v-if="result > 500000">!</span>
			<span v-if="result > 500000000">!</span>
			<span v-if="result > 5000000000000">!</span>
		</div>
	</div>
</template>

<script>
import InputNumber from '@/components/InputNumber'

export default {
	name: 'Home',

	data () {
		return {
			result: null
		}
	},

	components: {
		InputNumber
	}
}
</script>

<style lang="stylus" scoped>
.home
	text-align center
	margin auto
	padding 1rem

.result
	margin-top 1rem
	max-width calc(100vw - 2rem)

.number
	display block
	font 300 4rem/1 var(--font-stack-heading)
	overflow-wrap break-word
	margin-bottom 1rem
</style>

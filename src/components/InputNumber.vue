<template>
	<div class="input-number">
		<button class="decrement" @click="decrement()">-</button>
		<input type="number" ref="number" v-model="inputNumber" @input="combination(inputNumber)" @change="combination(inputNumber)" min="2">
		<button class="increment" @click="increment()">+</button>
	</div>
</template>

<script>
export default {
	name: 'InputNumber',

	emits: ['on-change'],

	data () {
		return {
			inputNumber: 2
		}
	},

	methods: {
		getAllNumbersBetween(x, y) {
			const numbers = []
			for (let i = x; i < y; i++) {
				numbers.push(i)
			}
			return numbers
		},

		combination (maxValue) {
			this.$emit('on-change', this.getAllNumbersBetween(1, maxValue).reduce((a, b) => a * b))
		},

		increment () {
			this.$refs.number.stepUp()
			this.inputNumber = this.$refs.number.value
			this.combination(this.inputNumber)
		},

		decrement () {
			this.$refs.number.stepDown()
			this.inputNumber = this.$refs.number.value
			this.combination(this.inputNumber)
		},
	}
}
</script>

<style lang="stylus" scoped>
.input-number
	display flex
	justify-content center

button
	font-size 2rem
	min-width 2em
	cursor pointer
	outline 0

.increment
	border-radius 0 .25em .25em 0

.decrement
	border-radius .25em 0 0 .25em

input
	font-size 2rem
	padding 1rem
	width 4em
	border-radius 0
	border-left 0
	border-right 0
	outline 0
	text-align center

	&::-webkit-inner-spin-button
	&::-webkit-outer-spin-button
		appearance none
		margin 0
</style>

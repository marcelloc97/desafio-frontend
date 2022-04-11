<template>
  <div :class="containerClasses">
		<span v-if="icon" name="icon" class="material-icons md-18" v-text="icon" />
		<span v-text="label" />
  </div>
</template>

<script>
export default {
  name: 'Button',
	props: {
		label: {
			type: String,
			default: 'Button'
		},

		icon: String,

		outline: {
			type: Boolean,
			default: () => false
		}
	},

	computed: {
		containerClasses() {
			return `button ${this.outline ? 'outline' : 'filled'} flex-row align-center`;
		}
	}
}
</script>

<style scoped>
.button {
	padding: 10px 18px;

	font-size: 0.8em;
	font-weight: bold;
	text-align: center;

	border-radius: 5px;
	transition: all 0.15s ease-in-out;

	cursor: pointer;
}
.button > span {
	user-select: none;
}
.button > span[name="icon"] {
	margin-right: 5px;
}

.filled {
	color: white;
	background: #007BFF;
	border: none;
}
.filled:hover {
	background: #0C9BF2;
}

.outline {
	color: #007BFF;
	background: none;
	border: 1px solid #007BFF;
}
.outline:hover {
	background: #0C9BF222;
	color: #0C9BF2;
	border-color: #0C9BF2;
}
</style>
<template>
  <div :class="containerClasses">
    <slot></slot>
  </div>
</template>

<script>
export default {
	name: 'Container',
	props: {
		row: Boolean,
		column: Boolean,

		'justify-start': Boolean, 
		'justify-center': Boolean, 
		'justify-between': Boolean, 
		'justify-evenly': Boolean, 
		'justify-around': Boolean, 
		'justify-end': Boolean,
		
		'align-start': Boolean,
		'align-center': Boolean,
		'align-end': Boolean
	},

	computed: {
		containerClasses() {
			const classes = ['container'];
			// const positionsMap = {
			// 	'start': 'Start',
			// 	'center': 'Center',
			// 	'between': 'Between',
			// 	'evenly': 'Evenly',
			// 	'around': 'Around',
			// 	'end': 'End'
			// };

			if (this.row) {
				classes.push('flex-row');
			} else if(this.column) {
				classes.push('flex-column');
			}

			// TODO: for justify and align, make it match in dynamic logic

			return classes;
		}
	}
}
</script>

<style scoped>
.container {
	padding: 16px;

	background: white;
	box-shadow: 0 2px 8px 0 #00000022;
	border-radius: 5px;
}
</style>
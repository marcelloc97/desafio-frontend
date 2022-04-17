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
		positionsMap() {
			return {
				'justifyStart': 'justify-start',
				'justifyCenter': 'justify-center',
				'justifyBetween': 'justify-between',
				'justifyEvenly': 'justify-evenly',
				'justifyAround': 'justify-around',
				'justifyEnd': 'justify-end',

				'alignStart': 'align-start',
				'alignCenter': 'align-center',
				'alignEnd': 'align-end'
			};
		},

		containerClasses() {
			const classes = ['container'];

			if (this.row) {
				classes.push('flex-row');
			} else if(this.column) {
				classes.push('flex-column');
			}

			// pegamos todas as chaves do nosso props
			const keys = Object.keys(this.$props);

			// filtramo-as com base nos caracteres maiúsculos
			const filteredKeys = keys.filter(key => /[A-Z]/g.exec(key));
			
			// rodamos as chaves filtradas e verificamos se o prop correspondente
			// foi chamado pelo componente pai
			filteredKeys.forEach(key => {
				if (this.$props[key]) {
					// adicionamos ao array e o vue faz o resto
					classes.push(this.positionsMap[key]);
				}
			});

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
<template>
  <div class="container">
    <slot></slot>
  </div>
</template>

<script>
export default {
	name: 'Container'
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
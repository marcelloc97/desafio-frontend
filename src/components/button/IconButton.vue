
<template>
  <button>
    <span class="material-icons md-18" v-text="icon" />
  </button>
</template>

<script>
export default {
  name: 'IconButton',

  props: {
    icon: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
button {
  width: 30px;
  height: 30px;
  padding: 5px;
  margin: 0;
  outline: none;

  border: none;
  background: none;
  border-radius: 50%;
  text-align: center;
  cursor: pointer;
}
button:hover {
  background: #F5F6F8;
}
button:active {
  background: #ebedf2;
}
</style>
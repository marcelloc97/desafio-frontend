
<template>
  <!-- 
    to implement
    https://www.npmjs.com/package/vue-material-design-icons
   -->
  <div id="layout">
    <Header />
  </div>
</template>

<script>
import Header from '../misc/Header.vue';

export default {
  name: 'MainLayout',

  components: {
    Header,
  },

  props: {},

  computed: {},

  data() {
    return {};
  },

  methods: {}
}
</script>

<style scoped>
#layout {
  width: 100%;
  height: 100vh;

  background: #F5F6F8;
  color: #3A3A3A;
}

/* #layout > .content {
  width: 80%;
  margin: auto;
} */
</style>
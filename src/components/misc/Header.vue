
<template>
  <header class="header-bg-color">
    <img
      :src="otLogo"
      alt="Oliveira Trust"
    />

    <UserInfo username="Marcello Carvalhal" />
  </header>
</template>

<script>
import logo from '../../assets/logo.svg';
import UserInfo from './UserInfo.vue';

export default {
  name: 'Header',
  components: {
    UserInfo
  },
  props: {},

  computed: {
    otLogo() {
      return logo;
    }
  },

  data() {
    return {};
  },

  methods: {}
}
</script>

<style scoped>
header {
  padding: 15px 100px;

  display: flex;
  align-items: center;
  justify-content: space-between;

  background: #FFFFFF;
}

img {
  width: 250px;
}
</style>

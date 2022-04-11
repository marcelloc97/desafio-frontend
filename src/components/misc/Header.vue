
<template>
  <header class="flex-row justify-between align-center">
    <img
      :src="otLogo"
      alt="Oliveira Trust"
    />

    <UserInfo :avatarUrl="avatarUrl" :username="username" />
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
  props: {
    username: String,
    avatarUrl: String
  },

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

  background: #FFFFFF;
}

img {
  width: 250px;
}
</style>

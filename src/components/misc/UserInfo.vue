
<template>
  <section class="flex-row justify-between align-center">
    <div class="avatar-container flex-row align-center">
      <Avatar :avatarUrl="avatarUrl" />
      <span v-text="username" />
    </div>

    <IconButton icon="logout" :size="18" @click="logout" />
  </section>
</template>

<script>
import Avatar from './Avatar.vue';
import IconButton from '../button/IconButton.vue';

export default {
  name: 'UserInfo',
  components: {
    Avatar,
    IconButton,
  },
  props: {
    avatarUrl: {
      type: String
    },

    username: {
      type: String,
      default: 'User',
      required: true
    }
  },

  methods: {
    logout() {
      console.log(`You've logged out! :)`);
    }
  }
}
</script>

<style scoped>
@import url('../../styles/classes.css');

.avatar-container {
  margin-right: 20px;
}
.avatar-container > span {
  font-size: 0.9em;
  font-weight: bold;
}
</style>

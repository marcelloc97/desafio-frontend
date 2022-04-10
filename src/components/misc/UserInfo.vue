
<template>
  <section class="container">
    <div class="avatar-container">
      <div class="avatar">
        <img :src="avatarUrl" :alt="username">
      </div>
      <span v-text="username" />
    </div>
    <button @click="logout">
      <span class="material-icons md-18">logout</span>
    </button>
  </section>
</template>

<script>
import AvatarImage from '../../assets/avatar.png';

export default {
  name: 'UserInfo',
  components: {},
  props: {
    avatarUrl: {
      type: String,
      default: () => AvatarImage,
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
.container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.avatar-container {
  margin-right: 20px;

  display: flex;
  align-items: center;
}
.avatar {
  width: 40px;
  height: 40px;
  margin-right: 10px;
  overflow: hidden;

  border-radius: 50%;
}
.avatar > img {
  width: 100%;
  height: 100%;
}
.avatar-container > span {
  font-size: 0.9em;
  font-weight: bold;
}

button {
  width: 30px;
  height: 30px;
  padding: 0;
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

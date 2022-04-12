
<template>
  <div class="avatar" :style="avatarStyle">
    <img :src="avatarUrl" />
  </div>
</template>

<script>
import AvatarImage from '../../assets/avatar.png';

export default {
  name: 'Avatar',
  props: {
    avatarUrl: {
      type: String,
      default: () => AvatarImage,
    },

    size: {
      type: [Number, String],
      default: 35
    },

    square: Boolean,
  },

  computed: {
    avatarStyle() {
      const styles = [
        `--size: ${this.size}px;`,
        `--radius: ${this.square ? 'none' : '50%'}`
      ];

      return styles.join(' ');
    }
  },
}
</script>

<style scoped>
.avatar {
  --size: 35px;
  --radius: 50%;

  width: var(--size);
  height: var(--size);
  margin-right: 10px;
  overflow: hidden;

  border-radius: var(--radius);
}
.avatar > img {
  width: 100%;
  height: 100%;
}
</style>
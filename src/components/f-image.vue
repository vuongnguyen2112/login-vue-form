<template>
  <div class="avatar">
      <img :src="image" alt="user-avatar">
    </div>
</template>

<script>
import image from '../assets/user_ava.png';

export default {
  name: 'fImage',
  data() {
    return {
      image
    }
  }
}
</script>

<style scoped>
.avt {
  user-select: none;
  max-width: 20%;
  margin: 20px 0;
}
img {
  display: block;
  width: 100%;
}
</style>
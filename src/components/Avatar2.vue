<template>
  <div class="avatar">
    <img :src="src" :alt="alt" :width="size" :height="size" />
  </div>
</template>

<script>
export default {
  name: 'Avatar',
  props: {
    src: {
      type: String,
      default: 'https://i.ibb.co/DDRxn8W/pp.jpg'
    },
    alt: {
      type: String
    },
    size: {
      type: Number
    }
  }
}
</script>

<style scoped>
.avatar {
  img {
    border-radius: 999px;
  }
}
</style>

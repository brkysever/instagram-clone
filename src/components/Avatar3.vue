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
      default:
        'https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/c0.180.1440.1440a/s640x640/68766037_2350481385213680_8964222389048199654_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_cat=108&_nc_ohc=zvK1yp6mF48AX9LMEPL&oh=f8d518e2df77c9d370a03fe6dd44d3ab&oe=5F845858'
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

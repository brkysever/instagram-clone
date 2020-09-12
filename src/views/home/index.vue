<template>
  <div class="home">
    <div class="timeline">
      <Post />
      <Post2 />
      <Post3 />
    </div>
    <div class="sidebar">
      <Sidebar />
    </div>
  </div>
</template>

<script>
import Post from '@/components/Post'
import Post2 from '@/components/Post2'
import Post3 from '@/components/Post3'
import Sidebar from '@/components/Sidebar'

export default {
  name: 'Home',
  components: { Post, Post2, Post3, Sidebar }
}
</script>

<style scoped>
.home {
  max-width: 605px;
  margin-left: auto;
  margin-right: auto;

  @media (--t) {
    max-width: none;
    display: grid;
    grid-template-columns: 1fr 295px;
    grid-gap: 30px;
  }
}
</style>

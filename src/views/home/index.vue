<template>
  <div class="home">
    <div class="timeline">
      <br />
      <br />
      <br />

      <Post />
      <Post2 />
      <Post3 />
    </div>
    <div class="sidebar">
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Id facilis
        veniam blanditiis molestiae illum libero rerum veritatis, officia nemo
        incidunt deserunt enim possimus cumque quis quidem adipisci cum
        laboriosam! Ad.
      </p>
    </div>
  </div>
</template>

<script>
import Post from '@/components/Post'
import Post2 from '@/components/Post2'
import Post3 from '@/components/Post3'

export default {
  name: 'Home',
  components: { Post, Post2, Post3 }
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

.sidebar {
  display: none;

  @media (--t) {
    display: block;
  }
}
</style>

<template>
  <div class="container">
    <img
      class="exploareimage"
      v-for="i of rows * 3"
      :key="i"
      :src="`${UNSPLASH_URL}${getRandomSize()}`"
    />
  </div>
</template>

<script>
export default {
  name: 'ComponentName',

  data() {
    return {
      UNSPLASH_URL: 'https://source.unsplash.com/random/',
      rows: 10
    }
  },

  methods: {
    getRandomSize() {
      return `${this.getRandomNr()}x${this.getRandomNr()}`
    },

    getRandomNr() {
      return Math.floor(Math.random() * 10) + 300
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

.container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;

  @media (--t) {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
  }
}

.exploareimage {
  object-fit: cover;
  padding: 5px;
  height: 300px;
  width: 300px;

  @media (--t) {
    object-fit: cover;
    padding: 10px;
    height: 300px;
    width: 300px;
    max-width: 100%;
    transition: 0.3s ease;
  }
}
</style>

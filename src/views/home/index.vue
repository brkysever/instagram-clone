<template>
  <div class="home">
    <div class="timeline">
      <Post
        v-for="post of postData"
        :key="post.mediaId"
        :media="post.media"
        :user-name="post.user.name"
        :avatar-url="post.user.avatarUrl"
        :last-comments="post.lastComments"
        :total-comment-count="post.totalCommentCount"
      />
    </div>
    <div class="sidebar">
      <Sidebar />
    </div>
  </div>
</template>

<script>
import Post from '@/components/Post'
import Sidebar from '@/components/Sidebar'

// Constant
const RESPONSE = [
  {
    user: {
      id: 1,
      name: 'brkysever',
      avatarUrl: 'https://i.imgur.com/xNmrE1v.jpg'
    },
    location: `Sant'Andrea della Valle`,
    media:
      'https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/s640x640/69252532_710543112749893_8501977450192107870_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_cat=101&_nc_ohc=07-PfXCU5J4AX-0vMPb&oh=fd04a97e40b385ecf59e3963558867e9&oe=5F8284CE',
    mediaId: 22,
    lastComments: [
      {
        commentId: 123,
        username: 'asd',
        comment: 'lol'
      },
      {
        commentId: 2442,
        username: '45234234',
        comment: 'asdfasdfasdf'
      }
    ],
    totalCommentCount: 2
  },
  {
    user: {
      id: 2,
      name: 'ogunb',
      avatarUrl:
        'https://instagram.fist7-1.fna.fbcdn.net/v/t51.2885-19/s320x320/49484222_339256583340316_1236206001422598144_n.jpg?_nc_ht=instagram.fist7-1.fna.fbcdn.net&_nc_ohc=cCsrL9-QDwEAX9Sue13&oh=b9d94ec54fc32c31febe70eebbbee490&oe=5F8F04A0'
    },
    location: `Çorlu`,
    media: 'https://i.ibb.co/DDRxn8W/pp.jpg',
    mediaId: 123,
    lastComments: [],
    totalCommentCount: 0
  },
  {
    user: {
      id: 3,
      name: 'arzum.sever',
      avatarUrl:
        'https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/c0.180.1440.1440a/s640x640/68766037_2350481385213680_8964222389048199654_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_cat=108&_nc_ohc=zvK1yp6mF48AX9LMEPL&oh=f8d518e2df77c9d370a03fe6dd44d3ab&oe=5F845858'
    },
    location: `Çorlu`,
    media:
      'https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/s640x640/70043480_118992722532617_4639210261878175229_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_cat=105&_nc_ohc=2ntt5RC0kGUAX_x6MTc&oh=81d91f0ac95154efae506caca9e7dcac&oe=5F853633',
    mediaId: 44,
    lastComments: [],
    totalCommentCount: 0
  },
  {
    user: {
      id: 4,
      name: 'trkakd',
      avatarUrl:
        'https://instagram.fist7-1.fna.fbcdn.net/v/t51.2885-19/s320x320/77136429_445559122824956_4368288237488177152_n.jpg?_nc_ht=instagram.fist7-1.fna.fbcdn.net&_nc_ohc=HG2Xp3qfMMgAX_yM_rJ&oh=da3115ce70bc873acc575f3253e58317&oe=5F91963F'
    },
    location: `Çorlu`,
    media:
      'https://instagram.fist7-2.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/s750x750/40479863_230845547787540_36484605680493892_n.jpg?_nc_ht=instagram.fist7-2.fna.fbcdn.net&_nc_cat=100&_nc_ohc=ZDtEh0a6jZgAX_r7h6I&oh=fcf58ca29af1448fe271430f1c24d7b0&oe=5F91A155',
    mediaId: 55,
    lastComments: [],
    totalCommentCount: 0
  }
]

export default {
  name: 'Home',

  components: { Post, Sidebar },

  data() {
    return {
      postData: []
    }
  },

  async created() {
    // get posts.
    const response = await fetch('https://jsonplaceholder.typicode.com/posts', {
      method: 'POST',
      body: JSON.stringify({
        title: 'foo',
        body: 'bar',
        userId: 1,
        asuidohauisd: '123'
      })
    })
    const json = await response.json()
    console.log(json)

    this.postData = RESPONSE
  }
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

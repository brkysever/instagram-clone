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
        :date="post.date"
        :myComment="post.myComment"
        :totalLike="post.totalLike"
        :location="post.location"
      />
    </div>
    <div class="sidebarHeader">
      <Avatar :size="60" />
      <CustomText tag="b">brkysever</CustomText>
      <CustomText size="small">Berkay Sever</CustomText>
      <div>
        <CustomText tag="b">Senin İçin Öneriler</CustomText>
      </div>

      <div>
        <Sidebar
          class="sidebar"
          v-for="sidebar of sidebarData"
          :key="sidebar.MediaId"
          :avatarUrl="sidebar.avatarUrl"
          :userName="sidebar.userName"
          :userInfo="sidebar.userInfo"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Post from '@/components/Post'
import Sidebar from '@/components/Sidebar'
import Avatar from '@/components/Avatar'
import CustomText from '@/components/CustomText'

// Constant
const RESPONSE2 = [
  {
    userName: 'user1',
    userInfo: 'asdasd',
    avatarUrl:
      'https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/s640x640/69252532_710543112749893_8501977450192107870_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_cat=101&_nc_ohc=07-PfXCU5J4AX-0vMPb&oh=fd04a97e40b385ecf59e3963558867e9&oe=5F8284CE'
  },
  {
    userName: 'aaa',
    userInfo: 'asdasd',
    avatarUrl:
      'https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/s640x640/69252532_710543112749893_8501977450192107870_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_cat=101&_nc_ohc=07-PfXCU5J4AX-0vMPb&oh=fd04a97e40b385ecf59e3963558867e9&oe=5F8284CE'
  },
  {
    userName: 'aaa',
    userInfo: 'asdasd',
    avatarUrl:
      'https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/s640x640/69252532_710543112749893_8501977450192107870_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_cat=101&_nc_ohc=07-PfXCU5J4AX-0vMPb&oh=fd04a97e40b385ecf59e3963558867e9&oe=5F8284CE'
  },
  {
    userName: 'aaa',
    userInfo: 'asdasd',
    avatarUrl:
      'https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/s640x640/69252532_710543112749893_8501977450192107870_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_cat=101&_nc_ohc=07-PfXCU5J4AX-0vMPb&oh=fd04a97e40b385ecf59e3963558867e9&oe=5F8284CE'
  }
]
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
    date: '30 DAKİKA ÖNCE',
    myComment: 'Art.',
    totalLike: '1,345',
    lastComments: [
      {
        commentId: 123,
        username: 'nicoke.a',
        comment: 'Nice'
      },
      {
        commentId: 124,
        username: 'skywalker',
        comment: '(Y)'
      }
    ],
    totalCommentCount: 1345
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
    date: '59 DAKİKA ÖNCE',
    myComment: ';)',
    totalLike: '85',
    lastComments: [
      {
        commentId: 1212,
        username: 'yodaoffical',
        comment: 'I don’t believe it.'
      }
    ],
    totalCommentCount: 85
  },
  {
    user: {
      id: 3,
      name: 'instagram',
      avatarUrl:
        'https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-19/s320x320/119381356_363756831450146_3008355575418576013_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_ohc=BMpoCdJah2YAX-ADzVw&oh=719db29f0c709d6a6ff3aece34b1868f&oe=5F907A8E'
    },
    media:
      'https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/p750x750/119793180_948494982317193_4988622005718016914_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_cat=1&_nc_ohc=q88C7UoKSE8AX_Ly60c&oh=dd2f0c58535ae59b993b58622f2008ac&oe=5F9084CC',
    mediaId: 22,
    date: '2 SAAT ÖNCE',
    myComment:
      'Cheer on Billy and the other amazing nominees at the 72nd Annual Emmy Awards. ⁣',
    totalLike: '5,345',
    lastComments: [
      {
        commentId: 126,
        username: 'jos.h',
        comment: 'Fantastic'
      },
      {
        commentId: 128,
        username: 't.todd',
        comment: 'My man.'
      }
    ],
    totalCommentCount: 5345
  },
  {
    user: {
      id: 4,
      name: 'trkakd',
      avatarUrl:
        'https://instagram.fist7-1.fna.fbcdn.net/v/t51.2885-19/s320x320/77136429_445559122824956_4368288237488177152_n.jpg?_nc_ht=instagram.fist7-1.fna.fbcdn.net&_nc_ohc=HG2Xp3qfMMgAX_yM_rJ&oh=da3115ce70bc873acc575f3253e58317&oe=5F91963F'
    },
    location: 'North Shield',
    media:
      'https://instagram.fist7-2.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/s750x750/40479863_230845547787540_36484605680493892_n.jpg?_nc_ht=instagram.fist7-2.fna.fbcdn.net&_nc_cat=100&_nc_ohc=ZDtEh0a6jZgAX_r7h6I&oh=fcf58ca29af1448fe271430f1c24d7b0&oe=5F91A155',
    mediaId: 55,
    date: '5 SAAT ÖNCE',
    lastComments: [],
    totalCommentCount: 48,
    totalLike: '48'
  }
]

export default {
  name: 'Home',

  components: { Post, Sidebar, Avatar, CustomText },

  data() {
    return {
      postData: [],
      sidebarData: []
    }
  },

  async created() {
    // get posts.

    this.postData = RESPONSE
    this.sidebarData = RESPONSE2
  }
}
</script>

<style scoped>
.home {
  max-width: 605px;
  margin-left: auto;
  margin-right: auto;
  padding-bottom: 80px;

  @media (--t) {
    max-width: none;
    display: grid;
    grid-template-columns: 1fr 295px;
    grid-gap: 30px;
  }
}
.sidebarHeader {
  display: flex;
  flex-direction: column;
}
</style>

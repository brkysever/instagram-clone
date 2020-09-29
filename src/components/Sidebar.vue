<template>
  <div class="sidebar">
    <div class="user">
      <Avatar :src="avatarUrl" :size="45" />
      <CustomText class="username" tag="b">{{ userName }}</CustomText>
    </div>
    <CustomText class="userinfo" size="xxsmall">{{ userInfo }}</CustomText>

    <div class="follow">
      <CustomText tag="b" size="small">Follow</CustomText>
    </div>
  </div>
</template>

<script>
import CustomText from '@/components/CustomText'
import Avatar from '@/components/Avatar'
export default {
  name: 'Sidebar',
  components: {
    CustomText,
    Avatar
  },

  props: {
    avatarUrl: {
      type: String,
      required: true
    },
    userName: {
      type: String,
      required: true
    },
    userInfo: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
.user {
  display: flex;
  flex-direction: inherit;
}
.username {
  margin-top: 10px;
  margin-left: 15px;
}

.userinfo {
  position: relative;
  left: 60px;
  bottom: 20px;
  color: rgba(var(--f52, 142, 142, 142), 1);
}
.t1 {
  margin-top: 50px;
  position: absolute;
  top: 75px;
  color: rgba(var(--f52, 142, 142, 142), 1);
}

.follow {
  position: relative;
  bottom: 45px;
  left: 250px;
  color: rgba(var(--d69, 0, 149, 246), 1);
}
</style>

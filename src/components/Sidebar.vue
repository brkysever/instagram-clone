<template>
  <div class="sidebar">
    <Avatar :size="55" />
    <div class="header-author-info">
      <div>
        <CustomText tag="b">brkysever</CustomText>
      </div>
      <div class="username">
        <CustomText size="small">Berkay Sever</CustomText>
      </div>
    </div>
    <div class="t1">
      <CustomText tag="b">Senin İçin Öneriler</CustomText>
    </div>

    <div class="user1">
      <img
        class="user"
        src="https://randomuser.me/api/portraits/men/32.jpg"
        alt=""
      />
      <div class="header-author-info">
        <div>
          <CustomText tag="b">s.stan</CustomText>
        </div>
        <div class="userinfo">
          <CustomText size="xxsmall">New to Instagram</CustomText>
        </div>
        <div class="follow">
          <CustomText tag="b" size="small">Takip Et</CustomText>
        </div>
      </div>
    </div>

    <div class="user2">
      <img
        class="user"
        src="https://randomuser.me/api/portraits/men/78.jpg"
        alt=""
      />
      <div class="header-author-info">
        <div>
          <CustomText tag="b">mariopalmer</CustomText>
        </div>
        <div class="userinfo">
          <CustomText size="xxsmall">Followed by ogoc</CustomText>
        </div>
        <div class="follow">
          <CustomText tag="b" size="small">Takip Et</CustomText>
        </div>
      </div>
    </div>

    <div class="user3">
      <img
        class="user"
        src="https://randomuser.me/api/portraits/women/2.jpg"
        alt=""
      />
      <div class="header-author-info">
        <div>
          <CustomText tag="b">eceakman</CustomText>
        </div>
        <div class="userinfo">
          <CustomText size="xxsmall">Followed by +2</CustomText>
        </div>
        <div class="follow">
          <CustomText tag="b" size="small">Takip Et</CustomText>
        </div>
      </div>
    </div>
    <div class="user4">
      <img
        class="user"
        src="https://randomuser.me/api/portraits/men/17.jpg"
        alt=""
      />
      <div class="header-author-info">
        <div>
          <CustomText tag="b">m.aslan</CustomText>
        </div>
        <div class="userinfo">
          <CustomText size="xxsmall">Followed by +4</CustomText>
        </div>
        <div class="follow">
          <CustomText tag="b" size="small">Takip Et</CustomText>
        </div>
      </div>
    </div>
    <div class="user5">
      <img
        class="user"
        src="https://randomuser.me/api/portraits/women/26.jpg"
        alt=""
      />
      <div class="header-author-info">
        <div>
          <CustomText tag="b">a.yilmaz</CustomText>
        </div>
        <div class="userinfo">
          <CustomText size="xxsmall">New to Instagram</CustomText>
        </div>
        <div class="follow">
          <CustomText tag="b" size="small">Takip Et</CustomText>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Avatar from '@/components/Avatar'
import CustomText from '@/components/CustomText'
export default {
  name: 'Sidebar',
  components: { Avatar, CustomText }
}
</script>

<style scoped>
.sidebar {
  cursor: pointer;
  position: fixed;
  display: flex;

  @media (--t) {
    cursor: pointer;
    display: flex;
    align-items: center;
  }
}
.header {
  height: 60px;
  display: flex;
  align-items: center;

  &-author {
    display: flex;

    &-info {
      margin-left: 16px;
    }
  }
}

.userinfo {
  color: rgba(var(--f52, 142, 142, 142), 1);
}
.t1 {
  margin-top: 50px;
  position: absolute;
  top: 75px;
  color: rgba(var(--f52, 142, 142, 142), 1);
}

.user {
  max-width: 40px;
  max-height: 40px;
  border-radius: 999px;
}
.follow {
  color: rgba(var(--d69, 0, 149, 246), 1);
  position: relative;
  left: 200px;
  top: -30px;
}
.user1 {
  position: absolute;
  display: flex;
  top: 150px;
}

.user2 {
  position: absolute;
  display: flex;
  top: 200px;
}
.user3 {
  position: absolute;
  display: flex;
  top: 250px;
}
.user4 {
  position: absolute;
  display: flex;
  top: 300px;
}
.user5 {
  position: absolute;
  display: flex;
  top: 350px;
}
</style>

<template>
  <div class="home">
    <button @click="showModal = true" class="moreicon">
      <img
        class="image"
        src="https://images.unsplash.com/photo-1600132012021-47de01ca0705?crop=entropy&cs=tinysrgb&fit=crop&fm=jpg&h=303&ixlib=rb-1.2.1&q=80&w=304"
        alt=""
      />
    </button>
    <transition name="fade" appear>
      <div
        class="modal-overlay"
        v-if="showModal"
        @click="showModal = false"
      ></div>
    </transition>
    <transition name="slide" appear>
      <div class="modal" v-if="showModal">
        <img
          class="image1"
          src="https://images.unsplash.com/photo-1600132012021-47de01ca0705?crop=entropy&cs=tinysrgb&fit=crop&fm=jpg&h=303&ixlib=rb-1.2.1&q=80&w=304"
        />
        <div class="modalAvatar">
          <Avatar />
          <CustomText tag="b" class="miniNick">brkysever</CustomText>
        </div>
        <div class="hrModal"></div>
        <div class="friendsProfile">
          <img
            class="user"
            src="https://randomuser.me/api/portraits/women/21.jpg"
            alt=""
          />
          <img
            class="user"
            src="https://randomuser.me/api/portraits/men/53.jpg"
            alt=""
          />
          <img
            class="user"
            src="https://randomuser.me/api/portraits/women/43.jpg"
            alt=""
          />
          <img
            class="user"
            src="https://randomuser.me/api/portraits/men/13.jpg"
            alt=""
          />
        </div>
        <div class="profileName">
          <CustomText size="small" tag="b" class="nt"
            >n.szr <CustomText> 👍</CustomText>
          </CustomText>

          <CustomText size="small" tag="b" class="nt"
            >kanye.east <CustomText>🌹</CustomText></CustomText
          >

          <CustomText size="small" tag="b" class="nt"
            >nicole.z <CustomText>🤔</CustomText></CustomText
          >
          <CustomText size="small" tag="b" class="nt"
            >frank-white <CustomText>😎👌 😍🕶️👌</CustomText></CustomText
          >
        </div>
        <div class="profileTime">
          <CustomText class="pT" size="small">
            <CustomText size="xsmall">79h</CustomText> 1beğenme
            Yanıtla</CustomText
          >
          <CustomText class="pT" size="small">
            <CustomText size="xsmall">78h</CustomText> 3beğenme
            Yanıtla</CustomText
          ><CustomText class="pT" size="small">
            <CustomText size="xsmall">77h</CustomText> 4beğenme
            Yanıtla</CustomText
          ><CustomText class="pT" size="small">
            <CustomText size="xsmall">69h</CustomText> 2beğenme
            Yanıtla</CustomText
          >
        </div>
        <div class="icons">
          <button type="button">
            <IconLike />
          </button>
          <button type="button">
            <IconComment />
          </button>
          <button type="button">
            <IconDirect />
          </button>
        </div>
        <div class="liker">
          <CustomText
            ><CustomText tag="b">arzum.sever</CustomText> ve
            <CustomText tag="b">diğer</CustomText> kişiler beğendi</CustomText
          >
        </div>
        <div class="datePhoto">
          <CustomText size="xsmall">
            15 Ağustos 2020
          </CustomText>
        </div>
      </div>
    </transition>

    <img
      class="image"
      src="https://images.unsplash.com/photo-1599167216067-9c069339880f?crop=entropy&cs=tinysrgb&fit=crop&fm=jpg&h=308&ixlib=rb-1.2.1&q=80&w=304"
      alt=""
    />
    <img
      class="image"
      src="https://images.unsplash.com/photo-1599971515566-342f7a54e548?crop=entropy&cs=tinysrgb&fit=crop&fm=jpg&h=308&ixlib=rb-1.2.1&q=80&w=304"
      alt=""
    />
    <img
      class="image"
      src="https://images.unsplash.com/photo-1599840296872-7653aa1db548?crop=entropy&cs=tinysrgb&fit=crop&fm=jpg&h=308&ixlib=rb-1.2.1&q=80&w=306"
      alt=""
    />
    <img
      class="image"
      src="https://images.unsplash.com/photo-1597965519123-caf92500a9f4?crop=entropy&cs=tinysrgb&fit=crop&fm=jpg&h=305&ixlib=rb-1.2.1&q=80&w=309"
      alt=""
    />
    <img
      class="image"
      src="https://images.unsplash.com/photo-1599799130521-f5d8b3901153?crop=entropy&cs=tinysrgb&fit=crop&fm=jpg&h=303&ixlib=rb-1.2.1&q=80&w=302"
      alt=""
    />
    <img
      class="image"
      src="https://images.unsplash.com/photo-1600409864933-921066854c78?crop=entropy&cs=tinysrgb&fit=crop&fm=jpg&h=303&ixlib=rb-1.2.1&q=80&w=306"
      alt=""
    />
    <img
      class="image"
      src="https://images.unsplash.com/photo-1599751449353-779b810ebb37?crop=entropy&cs=tinysrgb&fit=crop&fm=jpg&h=300&ixlib=rb-1.2.1&q=80&w=306"
      alt=""
    />
    <img
      class="image"
      src="https://images.unsplash.com/photo-1599569958048-2051d3f9a3e9?crop=entropy&cs=tinysrgb&fit=crop&fm=jpg&h=302&ixlib=rb-1.2.1&q=80&w=300"
      alt=""
    />
  </div>
</template>

<script>
import IconLike from '@/icons/like.svg'
import IconComment from '@/icons/comment.svg'
import IconDirect from '@/icons/direct.svg'
import Avatar from '@/components/Avatar'
import CustomText from '@/components/CustomText'
export default {
  name: 'ProfilePost',
  components: {
    Avatar,
    CustomText,
    IconDirect,
    IconLike,
    IconComment
  },
  data() {
    return {
      showModal: false
    }
  }
}
</script>

<style>
.datePhoto {
  position: absolute;
  left: 660px;
  bottom: 60px;
  color: gray;
}
.liker {
  position: absolute;
  left: 660px;
  bottom: 80px;
}
.icons {
  position: absolute;
  left: 660px;
  bottom: 100px;
  button {
    margin-right: 16px;
  }
}
.hrModal {
  position: absolute;
  top: 70px;
  left: 655px;
  width: 343px;
  box-shadow: 0px 0px 1px 1px rgba(231, 231, 231, 0.86);
}
.miniNick {
  position: absolute;
  left: 55px;
  bottom: 20px;
}
.modalAvatar {
  width: 45px;
  height: 45px;
  position: absolute;
  left: 662px;
  bottom: 550px;
}
.pT {
  margin-bottom: 42px;
  color: gray;
}
.nt {
  margin-bottom: 42px;
}
.profileTime {
  display: flex;
  flex-flow: column;
  position: absolute;
  left: 720px;
  bottom: 210px;
}
.profileName {
  display: flex;
  flex-direction: column;
  position: absolute;
  left: 720px;
  bottom: 230px;
}
.friendsProfile {
  position: absolute;
  left: 670px;
  bottom: 245px;
  display: flex;
  flex-direction: column;
}
.user {
  margin-bottom: 15px;
  width: 40px;
  height: 40px;
  border-radius: 99px;
}
.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 99;
  width: 100%;
  max-width: 1000px;
  background-color: #fff;
  padding: 2px;
}
.modal-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 98;
  background-color: rgba(0, 0, 0, 0.3);
}
.fade-leave-to {
  opacity: 1;
}
.home {
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
.image1 {
  width: 650px;
  height: 600px;
}
.image {
  object-fit: cover;
  padding: 8px;
  height: 310px;
  width: 310px;
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

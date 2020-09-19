<template>
  <div class="profile">
    <div class="profileCard">
      <button class="button" @click="showModal = true">
        <Avatar class="profilAvatar" />
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
          <customText class="modalText" tag="p"
            >Profil Fotoğrafını Değiştir</customText
          >
          <customText class="modalText2" tag="p" size="small"
            >Fotoğraf Yükle</customText
          >

          <customText class="modalText3" tag="p" size="small"
            >Mevcut Fotoğrafı Kaldır</customText
          >
        </div>
      </transition>

      <!-- ------------------------------------------------ -->
      <div class="card">
        <Customtext class="nick">brkysever</Customtext>
        <button class="settingButton">Profili Düzenle</button>
      </div>
      <!-- ------------------------------------------------ -->

      <button @click="showModal2 = true" class="moreicon">
        <IconMore />
      </button>

      <transition name="fade" appear>
        <div
          class="modal-overlay"
          v-if="showModal2"
          @click="showModal2 = false"
        ></div>
      </transition>
      <transition name="slide" appear>
        <div class="modal" v-if="showModal2">
          <CustomText size="small" tag="p" class="modalText5"
            >Şifreyi Değiştir</CustomText
          >
          <CustomText size="small" tag="p" class="modalText4"
            >Ad Etiketi</CustomText
          >
          <CustomText size="small" tag="p" class="modalText4"
            >Uygulamalar ve İnternet Siteleri
          </CustomText>
          <CustomText size="small" tag="p" class="modalText4"
            >Bildirimler</CustomText
          >
          <CustomText size="small" tag="p" class="modalText4"
            >Gizlilik ve Güvenlik</CustomText
          >
          <CustomText size="small" tag="p" class="modalText4"
            >Giriş Hareketleri</CustomText
          >
          <CustomText size="small" tag="p" class="modalText4"
            >Instagram'dan E-postalar</CustomText
          >
          <CustomText size="small" tag="p" class="modalText4"
            >Sorun Bildirimler</CustomText
          >
          <CustomText size="small" tag="p" class="modalText4"
            >Çıkış Yap</CustomText
          >
        </div>
      </transition>
      <div class="followers">
        <CustomText class="fn" tag="b">9</CustomText>
        <CustomText class="fs">gönderi </CustomText>
        <CustomText class="fn" tag="b">152</CustomText>
        <CustomText class="fs">takipçi</CustomText>
        <CustomText class="fn" tag="b">359</CustomText>
        <CustomText class="fs">takip</CustomText>
      </div>
    </div>
    <div class="hr"></div>
    <div class="nav">
      <router-link class="rL" to="/profile">Post</router-link>
      <router-link class="rL" to="/profile/igtv">IGTV</router-link>
      <router-link class="rL" to="/profile/save">Save</router-link>
      <router-link class="rL" to="/profile/tag">Tag</router-link>
    </div>

    <router-view />
  </div>
</template>

<script>
import CustomText from '@/components/CustomText'
import Avatar from '@/components/Avatar'
import IconMore from '@/icons/more.svg'
export default {
  name: 'Profile',
  components: {
    Avatar,
    CustomText,
    IconMore
  },
  data() {
    return {
      showModal: false,
      showModal2: false
    }
  }
}
</script>

<style scoped>
.hr {
  position: relative;
  top: 75px;
  max-width: 100%;
  box-shadow: 0px 0px 1px 1px rgba(231, 231, 231, 0.86);
  @media (--t) {
    position: relative;
    top: 100px;
    max-width: 100%;
    box-shadow: 0px 0px 1px 1px rgba(231, 231, 231, 0.86);
  }
}
.nav {
  display: flex;
  justify-content: center;
  padding-top: 80px;
  padding-right: 60px;
  @media (--t) {
    display: flex;
    justify-content: center;
    padding-top: 110px;
    padding-right: 100px;
  }
}
.rL {
  font-weight: lighter;
  color: rgba(var(--i1d, 38, 38, 38), 1);
  font-size: 17px;
  padding-left: 60px;
  @media (--t) {
    font-weight: lighter;
    color: rgba(var(--i1d, 38, 38, 38), 1);
    font-size: 17px;
    padding-left: 100px;
  }
}
.fn {
  cursor: pointer;
  padding-right: 3px;
  font-size: 13px;
  @media (--t) {
    padding-right: 3px;
    font-size: 15px;
  }
}
.fs {
  cursor: pointer;
  padding-right: 15px;
  font-weight: lighter;
  font-size: 12px;
  @media (--t) {
    padding-right: 15px;
    font-weight: lighter;
    font-size: 15px;
  }
}
.followers {
  display: flex;
  position: relative;
  right: 210px;
  top: 70px;
  @media (--t) {
    display: flex;
    position: relative;
    right: 315px;
    top: 50px;
  }
}
.profileCard {
  display: flex;
}
.moreicon {
  margin-top: -55px;
  margin-right: 80px;
  @media (--t) {
    width: 1px;
    height: 1px;
    margin-top: 15px;
    margin-left: 15px;
  }
}
.profilAvatar {
  width: 120px;
  margin-left: 20px;
  margin-top: -20px;
  @media (--t) {
    width: 150px;
    margin-left: 80px;
    margin-top: -10px;
  }
}
.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 99;
  width: 70%;
  max-width: 400px;
  background-color: #fff;
  border-radius: 16px;
  padding: 25px;
  @media (--t) {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 99;
    width: 50%;
    max-width: 400px;
    background-color: #fff;
    border-radius: 16px;
    padding: 25px;
  }
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
.fade-enter,
.fade-leave-to {
  opacity: 1;
}
.modalText {
  font-size: 16px;
  cursor: pointer;
  line-height: 1.5;
  min-height: 40px;
  text-align: center;
  font-weight: 500;
}
.modalText2 {
  border-top: 1px solid rgba(var(--b6a, 219, 219, 219), 1);
  cursor: pointer;
  line-height: 1.5;
  min-height: 50px;
  padding: 15px;
  text-align: center;
  font-weight: 700;
  color: rgb(65, 174, 241);
}
.modalText3 {
  border-top: 1px solid rgba(var(--b6a, 219, 219, 219), 1);
  cursor: pointer;
  line-height: 1.5;
  padding-top: 20px;
  text-align: center;
  font-weight: 700;
  color: rgb(236, 53, 53);
}
.modalText4 {
  border-top: 1px solid rgba(var(--b6a, 219, 219, 219), 1);
  cursor: pointer;
  line-height: 1.5;
  padding-top: 10px;
  padding-bottom: 10px;
  text-align: center;
}
.modalText5 {
  cursor: pointer;
  line-height: 1.5;
  padding-bottom: 10px;
  text-align: center;
}
.nick {
  padding-left: 20px;
  font-size: 25px;
  font-weight: lighter;
  color: rgba(var(--i1d, 38, 38, 38), 1);
  @media (--t) {
    padding-left: 70px;
    font-size: 28px;
    font-weight: lighter;
    color: rgba(var(--i1d, 38, 38, 38), 1);
  }
}
.settingButton {
  background-color: transparent;
  border: 1px solid rgba(var(--ca6, 219, 219, 219), 1);
  border-radius: 4px;
  cursor: pointer;
  font-weight: 200;
  padding: 5px 9px;
  text-align: center;
  margin-left: 10px;
  @media (--t) {
    background-color: transparent;
    border: 1px solid rgba(var(--ca6, 219, 219, 219), 1);
    color: rgba(var(--f75, 38, 38, 38), 1);
    border-radius: 4px;
    box-sizing: border-box;
    cursor: pointer;
    font-weight: 600;
    padding: 5px 9px;
    text-align: center;
    margin-left: 10px;
  }
}
.button {
  outline: transparent;
}
</style>

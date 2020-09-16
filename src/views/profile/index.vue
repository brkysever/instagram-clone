<template>
  <div class="home">
    <header>
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
      <div class="moreicon">
        <button @click="showModal2 = true">
          <IconMore />
        </button>
      </div>
      <transition name="fade" appear>
        <div
          class="modal-overlay2"
          v-if="showModal2"
          @click="showModal2 = false"
        ></div>
      </transition>
      <transition name="slide" appear>
        <div class="modal2" v-if="showModal2">
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
      <div class="nick">
        <customtext>brkysever</customtext>
        <button class="settingButton">Profili Düzenle</button>
      </div>
    </header>

    <div id="nav">
      <router-link to="/profile">Post</router-link> |
      <router-link to="/profile/igtv">IGTV</router-link> |
      <router-link to="/profile/save">Save</router-link> |
      <router-link to="/profile/tag">Tag</router-link>
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

<style>
.button {
  outline: transparent;
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
.modal-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 98;
  background-color: rgba(0, 0, 0, 0.3);
}
.modal {
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
.modal2 {
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
.modal-overlay2 {
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
.profilAvatar {
  width: 100px;
  padding-left: 10px;
  margin-top: -20px;
  @media (--t) {
    width: 150px;
    position: relative;
    margin-left: 50px;
  }
}
.nick {
  font-size: 20px;
  color: rgba(var(--i1d, 38, 38, 38), 1);
  position: relative;
  bottom: 60px;
  left: 125px;

  @media (--t) {
    position: relative;
    bottom: 120px;
    left: 250px;
    font-size: 28px;
    color: rgba(var(--i1d, 38, 38, 38), 1);
  }
}
.settingButton {
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
.moreicon {
  position: relative;
  top: -30px;
  left: 350px;
  z-index: 1;
  @media (--t) {
    position: relative;
    top: -80px;
    left: 500px;
    z-index: 1;
  }
}
</style>

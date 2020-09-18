<template>
  <div class="profile">
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
    <div class="nick">
      <customtext>brkysever</customtext>
      <button class="settingButton">Profili Düzenle</button>
    </div>

    <div id="nav">
      <router-link to="/profile">Post</router-link> |
      <router-link to="/profile/igtv">IGTV</router-link> |
      <router-link to="/profile/save">Save</router-link> |
      <router-link to="/profile/tag">Tag</router-link>
    </div>

    <router-view />
    h
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

<style></style>

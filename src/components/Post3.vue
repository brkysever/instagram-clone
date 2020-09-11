<template>
  <div class="post">
    <header class="header section">
      <div class="header-author">
        <Avatar3 :size="40" />
        <div class="header-author-info">
          <div>
            <CustomText tag="b">arzum.sever</CustomText>
          </div>
          <div>
            <CustomText size="xsmall">Fontana Di Trevi</CustomText>
          </div>
        </div>
      </div>
      <div class="header-more">
        <button type="button">
          <IconMore />
        </button>
      </div>
    </header>

    <!-- media -->
    <div class="post-media">
      <img
        src="https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/s640x640/70043480_118992722532617_4639210261878175229_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_cat=105&_nc_ohc=2ntt5RC0kGUAX_x6MTc&oh=81d91f0ac95154efae506caca9e7dcac&oe=5F853633"
        alt=""
      />
    </div>

    <!-- actions -->
    <div class="action-buttons section">
      <button type="button">
        <IconLikeFill />
      </button>
      <button type="button">
        <IconComment />
      </button>
      <button type="button">
        <IconDirect />
      </button>
      <button class="action-save" type="button">
        <IconSave />
      </button>
    </div>

    <div class="view-count section">
      <custom-text tag="b">2.485 beğenme</custom-text>
    </div>
    <div class="view-count section">
      <custom-text tag="b">arzum.sever</custom-text>
      <custom-text> Zengin fakir ayrılsın.</custom-text>
    </div>
    <div class="comment section">
      <custom-text>89 yorumun tümünü gör </custom-text>
    </div>
    <div class="view-count section">
      <custom-text tag="b">annacoach </custom-text>
      <custom-text>Beautiful picture👍</custom-text>
    </div>
    <div class="view-count section">
      <custom-text tag="b">jenniferlu </custom-text>
      <custom-text>Roads of Rome</custom-text>
    </div>
    <div class="comment section">
      <custom-text class="xxsmall">1 SAAT ÖNCE</custom-text>
    </div>

    <br />
  </div>
</template>

<script>
import Avatar3 from '@/components/Avatar3'
import CustomText from '@/components/CustomText'
import IconMore from '@/icons/more.svg'
import IconLikeFill from '@/icons/like-fill.svg'
import IconComment from '@/icons/comment.svg'
import IconDirect from '@/icons/direct.svg'
import IconSave from '@/icons/save.svg'

export default {
  name: 'Post',
  components: {
    IconLikeFill,
    IconComment,
    IconDirect,
    IconSave,
    IconMore,
    CustomText,
    Avatar3
  }
}
</script>

<style scoped>
.post {
  margin-top: 60px;
  margin-bottom: 60px;
  border-radius: 3px;
  border: 1px solid rgb(var(--b6a));
  background-color: white;
}

.section {
  padding-top: 8px;
  padding-left: 16px;
  padding-right: 16px;
}

.comment {
  color: rgba(var(--f52, 142, 142, 142), 1);
}

.header {
  height: 60px;
  display: flex;
  align-items: center;

  &-author {
    display: flex;
    align-items: center;

    &-info {
      margin-left: 8px;
    }
  }

  &-more {
    margin-left: auto;
  }
}

.action-buttons {
  height: 45px;
  display: flex;
  align-items: center;

  button {
    margin-right: 16px;
  }

  .action-save {
    margin-left: auto;
    margin-right: 0;
  }
}
</style>

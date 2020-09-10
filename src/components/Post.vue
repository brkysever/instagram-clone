<template>
  <div class="post">
    <!-- header -->
    <header class="header section">
      <div class="header-author">
        <Avatar :size="40" />
        <div class="header-author-info">
          <div>
            <CustomText tag="b">brkysever</CustomText>
          </div>
          <div>
            <CustomText size="xsmall">Sant'Andrea della Valle</CustomText>
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
        src="https://instagram.fist13-1.fna.fbcdn.net/v/t51.2885-15/sh0.08/e35/s640x640/69252532_710543112749893_8501977450192107870_n.jpg?_nc_ht=instagram.fist13-1.fna.fbcdn.net&_nc_cat=101&_nc_ohc=07-PfXCU5J4AX-0vMPb&oh=fd04a97e40b385ecf59e3963558867e9&oe=5F8284CE"
        alt=""
      />
    </div>

    <!-- actions -->
    <div class="action-buttons section">
      <button type="button">
        <IconLike />
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
      <custom-text tag="b">1.345 beğenme</custom-text>
    </div>
    <div class="view-count section">
      <custom-text tag="b">brkysever </custom-text>
      <custom-text>Sant'Andrea della Valle</custom-text>
    </div>
    <div class="comment section">
      <custom-text>48 yorumun tümünü gör </custom-text>
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
      <custom-text class="xxsmall">30 DAKİKA ÖNCE</custom-text>
    </div>

    <br />
    <br />
    <br />
    <br />
    <br />
    <br />

    <!-- comment list -->

    <!-- datetime -->

    <!-- comment form -->
  </div>
</template>

<script>
import Avatar from '@/components/Avatar'
import CustomText from '@/components/CustomText'
import IconMore from '@/icons/more.svg'
import IconLike from '@/icons/like.svg'
import IconComment from '@/icons/comment.svg'
import IconDirect from '@/icons/direct.svg'
import IconSave from '@/icons/save.svg'

export default {
  name: 'Post',
  components: {
    IconLike,
    IconComment,
    IconDirect,
    IconSave,
    IconMore,
    CustomText,
    Avatar
  }
}
</script>

<style scoped>
.post {
  border-radius: 3px;
  border: 1px solid rgb(var(--b6a));
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

<template>
  <div class="post">
    <header class="header section">
      <div class="header-author">
        <Avatar2 :size="40" />
        <div class="header-author-info">
          <div>
            <CustomText tag="b">ogocanb</CustomText>
          </div>
          <div>
            <CustomText size="xsmall"></CustomText>
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
      <img src="https://i.ibb.co/DDRxn8W/pp.jpg" alt="" />
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
      <custom-text tag="b">1 beğenme</custom-text>
    </div>
    <div class="view-count section">
      <custom-text tag="b">ogocanb</custom-text>
      <custom-text></custom-text>
    </div>
    <div class="comment section">
      <custom-text>1 yorumun tümünü gör </custom-text>
    </div>
    <div class="view-count section">
      <custom-text tag="b">mariopalmer </custom-text>
      <custom-text>👍</custom-text>
    </div>
    <div class="view-count section">
      <custom-text tag="b">nico.b </custom-text>
      <custom-text>Nice</custom-text>
    </div>
    <div class="comment section">
      <custom-text class="xxsmall">45 DAKİKA ÖNCE</custom-text>
    </div>

    <br />
  </div>
</template>

<script>
import Avatar2 from '@/components/Avatar2'
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
    Avatar2
  }
}
</script>

<style scoped>
.post {
  margin-top: 60px;
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

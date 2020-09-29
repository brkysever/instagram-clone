<template>
  <div class="post">
    <!-- header -->
    <header class="header section">
      <div class="header-author">
        <Avatar :src="avatarUrl" :size="40" />

        <div class="header-author-info">
          <div>
            <CustomText tag="b">{{ userName }}</CustomText>
          </div>
          <div>
            <CustomText size="xsmall">{{ location }}</CustomText>
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
      <img :src="media" />
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
      <custom-text tag="b"> {{ totalLike }} beğenme</custom-text>
    </div>

    <div class="view-count section">
      <custom-text tag="b">{{ userName }} </custom-text>
      <custom-text> {{ myComment }}</custom-text>
    </div>

    <div class="comment section" v-if="totalCommentCount">
      <custom-text>{{ totalCommentCount }} yorumun tümünü gör </custom-text>
    </div>

    <div
      v-for="comment of lastComments"
      :key="comment.commentId"
      class="view-count section"
    >
      <custom-text tag="b">{{ comment.username }} </custom-text>
      <custom-text>{{ comment.comment }}</custom-text>
    </div>

    <div class="comment section">
      <custom-text class="xxsmall"> {{ date }}</custom-text>
    </div>

    <br />
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
  },

  props: {
    userName: {
      type: String,
      required: true
    },
    avatarUrl: {
      type: String,
      required: true
    },
    location: {
      type: String,
      required: true
    },
    media: {
      type: String,
      required: true
    },
    totalCommentCount: {
      type: Number,
      default: 0
    },
    lastComments: {
      type: Array,
      default: () => []
    },
    date: {
      type: String,
      required: true
    },
    myComment: {
      type: String,
      required: true
    },
    totalLike: {
      type: String,
      default: '0'
    }
  }
}
</script>

<style scoped>
.post {
  border-radius: 3px;
  border: 1px solid rgb(var(--b6a));
  background-color: white;
  margin-bottom: 20px;
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

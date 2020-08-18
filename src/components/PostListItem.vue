<template>
  <div class="post">
    <div class="user-info">
      <a href="#" class="user-name">{{user.name}}</a>
      <a href="#">
        <img class="avatar-large" :src="user.avatar" alt="">
      </a>
      <p>{{userPostsCount}}</p>
    </div>
    <div class="post-content">
      <div>
        <p>
          {{post.text}}
        </p>
      </div>
    </div>
    <div class="post-date text-faded">
      {{post.publishedAt}}
    </div>
  </div>
</template>

<script>
  import sourceData from '@/data'

  export default {
    name: 'PostListItem',
    props: {
      post: {
        required: true,
        type: Object
      }
    },
    computed: {
      user: function () {
        return sourceData.users[this.post.userId]
      },
      userPostsCount () {
        let counter = Object.keys(this.user.posts).length
        let suffix = counter > 1 ? ' posts' : ' post'
        return counter + suffix
      }
    }
  }
</script>

<style scoped>

</style>

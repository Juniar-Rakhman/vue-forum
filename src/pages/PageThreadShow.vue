<template>
  <div class="col-large push-top">
    <h1>{{ thread.title }}</h1>
    <PostList :posts="posts"/>
  </div>
</template>

<script>
  import sourceData from '@/data.json'
  import PostList from '@/components/PostList'

  export default {
    components: {
      PostList
    },
    props: {
      id: {
        required: true,
        type: String
      }
    },
    data () {
      return {
        thread: sourceData.threads[this.id]
      }
    },
    computed: {
      posts () {
        const postIds = Object.values(this.thread.posts)
        return Object.values(sourceData.posts)
          .filter(function (post) {
            return postIds.includes(post['.key'])
          })
      }
    }
  }
</script>

<style scoped>

</style>

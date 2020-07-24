<template>
  <div>
  </div>
</template>

<script>
  import sourceData from '@/data'

  export default {
    name: 'HelloWorld',
    data () {
      return {
        threads: sourceData.threads,
        posts: sourceData.posts,
        users: sourceData.users
      }
    }
  }
</script>

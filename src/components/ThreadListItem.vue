<template>
  <div class="thread">
    <div>
      <p>
        <router-link :to="{name: 'ThreadShow', params: {id: thread['.key']}}">{{thread.title}}</router-link>
      </p>
      <p class="text-faded text-xsmall"> By <a href="#">{{user}}</a>{{thread.publishedAt}}</p>
    </div>

    <div class="activity">
      <p class="replies-count">
        {{repliesCount}}
      </p>
<!--
            <img class="avatar-medium"
                 src="http://i0.kym-cdn.com/photos/images/facebook/000/010/934/46623-batman_pikachu_super.png" alt="">

            <div>
              <p class="text-xsmall">
                <a href="#">Bruce Wayne</a>
              </p>
              <p class="text-xsmall text-faded">2 hours ago</p>
            </div>
-->
    </div>
  </div>
</template>

<script>
  import sourceData from '@/data'

  export default {
    name: 'ThreadListItem',
    props: {
      thread: {
        required: true,
        type: Object
      }
    },
    computed: {
      repliesCount () {
        let counter = Object.keys(this.thread.posts).length - 1
        let suffix = counter > 1 ? ' replies' : ' reply'
        return counter + suffix
      },
      user () {
        return sourceData.users[this.thread.userId].name
      }
    }
  }
</script>

<style scoped>

</style>

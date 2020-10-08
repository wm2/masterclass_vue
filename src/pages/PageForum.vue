<template>
    <div class="col-full push-top">

            <ul class="breadcrumbs">
              <li><a href="/index.html"><i class="fa fa-home fa-btn"></i>Home</a></li>
              <li><a href="/category.html">Discussions</a></li>
              <li class="active"><a href="#">Cooking</a></li>
            </ul>

      <div class="forum-header">
        <div class="forum-details">
          <h1>{{ forum.name }}</h1>
          <p class="text-lead">{{ forum.description }}</p>
        </div>
        <a href="new-thread.html" class="btn-green btn-small">Start a thread</a>
      </div>
          <div class="col-full">
              <ThreadList :threads="threads"/>
          </div>
    </div>

<!--    <div class="col-full">-->
<!--        <ThreadList :threads="threads"/>-->
<!--    </div>-->
</template>

<script>
import ThreadList from '../components/ThreadList'

export default {
  name: 'PageForum',
  components: {
    ThreadList
  },
  props: {
    id: {
      required: true,
      type: String
    }
  },
  computed: {
    forum () {
      return this.$store.state.forums[this.id]
    },
    threads () {
      return Object.values(this.$store.state.threads)
        .filter(thread => thread.forumId === this.id)
    }
  }
}
</script>

<style scoped>
  .forum-wrapper {
    width: 100%
  }
</style>

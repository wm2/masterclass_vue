<template>
  <div class="col-large push-top">

    <!--    <ul class="breadcrumbs">-->
    <!--      <li><a href="#"><i class="fa fa-home fa-btn"></i>Home</a></li>-->
    <!--      <li><a href="category.html">Discussions</a></li>-->
    <!--      <li class="active"><a href="#">Cooking</a></li>-->
    <!--    </ul>-->

    <h1>{{ thread.title }}</h1>

    <p>
      By <a href="#" class="link-unstyled">Robin</a>, <AppDate :timestamp="thread.publishedAt"/>.
      <span style="float:right; margin-top: 2px;" class="hide-mobile text-faded text-small">3 replies by 3 contributors</span>
    </p>
    <PostList
      :posts="posts"/>
    <PostEditor
      :threadId="id"
    />


  </div>
</template>

<script>

import PostList from '../components/PostList'
import PostEditor from '../components/PostEditor'

export default {
  components: {
    PostList,
    PostEditor
  },
  props: {
    id: {
      required: true,
      type: String
    }
  },
  computed: {
    posts () {
      const postIds = Object.values(this.thread.posts)
      return Object.values(this.$store.state.posts).filter(post => postIds.includes(post['.key']))
    },
    thread () {
      return this.$store.state.threads[this.id]
    }
  }
}
</script>


<!--<div class="post-list">-->
<!--<div v-for="postId in thread.posts" class="post">-->

<!--  <div class="user-info">-->
<!--    <a href="#" class="user-name">{{ users[posts[postId].userId].name }}</a>-->

<!--    <a href="#">-->
<!--      <img class="avatar-large" :src="users[posts[postId].userId].avatar" alt="">-->
<!--    </a>-->

<!--    <p class="desktop-only text-small">107 posts</p>-->

<!--    <p class="desktop-only text-small">23 threads</p>-->

<!--    <span class="online desktop-only">online</span>-->

<!--  </div>-->

<!--  <div class="post-content">-->
<!--    <div>-->
<!--      <p>-->
<!--        {{ posts[postId].text }}-->
<!--      </p>-->
<!--    </div>-->
<!--    &lt;!&ndash;          <a href="#" style="margin-left: auto;" class="link-unstyled" title="Make a change"><i class="fa fa-pencil"></i></a>&ndash;&gt;-->
<!--  </div>-->


<!--  <div class="post-date text-faded">-->
<!--    {{ posts[postId].publishedAt }}-->
<!--  </div>-->

<!--  &lt;!&ndash;        <div class="reactions">&ndash;&gt;-->
<!--  &lt;!&ndash;          <ul>&ndash;&gt;-->
<!--  &lt;!&ndash;            <li>💡</li>&ndash;&gt;-->
<!--  &lt;!&ndash;            <li>❤️</li>&ndash;&gt;-->
<!--  &lt;!&ndash;            <li>👎</li>&ndash;&gt;-->
<!--  &lt;!&ndash;            <li>👍</li>&ndash;&gt;-->
<!--  &lt;!&ndash;            <li>👌</li>&ndash;&gt;-->
<!--  &lt;!&ndash;          </ul>&ndash;&gt;-->
<!--  &lt;!&ndash;          <button class="btn-xsmall"><span class="emoji">❤️</span>️ 3</button>&ndash;&gt;-->
<!--  &lt;!&ndash;          <button class="btn-xsmall active-reaction"><span class="emoji">👌️</span>️ 1</button>&ndash;&gt;-->
<!--  &lt;!&ndash;          <button class="btn-xsmall">+ <i class="fa fa-smile-o emoji"></i></button>&ndash;&gt;-->
<!--  &lt;!&ndash;        </div>&ndash;&gt;-->

<!--</div>-->
<!--</div>-->

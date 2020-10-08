<template>
  <div class="col-full">
    <h1>Welcome to the Forum</h1>
    <CategoryList :categories="categories"/>
  </div>
</template>

<script>
import CategoryList from '../components/CategoryList'

export default {
  components: {
    CategoryList
  },
  computed: {
    categories () {
      return Object.values(this.$store.state.categories)
    }
  }
}
</script>


<!--<div>-->
<!--<div v-for="thread in forums" class="col-large push-top">-->

<!--  &lt;!&ndash;    <ul class="breadcrumbs">&ndash;&gt;-->
<!--  &lt;!&ndash;      <li><a href="#"><i class="fa fa-home fa-btn"></i>Home</a></li>&ndash;&gt;-->
<!--  &lt;!&ndash;      <li><a href="category.html">Discussions</a></li>&ndash;&gt;-->
<!--  &lt;!&ndash;      <li class="active"><a href="#">Cooking</a></li>&ndash;&gt;-->
<!--  &lt;!&ndash;    </ul>&ndash;&gt;-->

<!--  <h1>{{ thread.title }}</h1>-->

<!--  &lt;!&ndash;    <p>&ndash;&gt;-->
<!--  &lt;!&ndash;      By <a href="#" class="link-unstyled">Robin</a>, 2 hours ago.&ndash;&gt;-->
<!--  &lt;!&ndash;      <span style="float:right; margin-top: 2px;" class="hide-mobile text-faded text-small">3 replies by 3 contributors</span>&ndash;&gt;-->
<!--  &lt;!&ndash;    </p>&ndash;&gt;-->

<!--  <div class="post-list">-->
<!--    <div v-for="postId in thread.posts" class="post">-->

<!--      <div class="user-info">-->
<!--        <a href="#" class="user-name">{{ users[posts[postId].userId].name }}</a>-->

<!--        <a href="#">-->
<!--          <img class="avatar-large" :src="users[posts[postId].userId].avatar" alt="">-->
<!--        </a>-->

<!--        <p class="desktop-only text-small">107 posts</p>-->

<!--        <p class="desktop-only text-small">23 forums</p>-->

<!--        <span class="online desktop-only">online</span>-->

<!--      </div>-->

<!--      <div class="post-content">-->
<!--        <div>-->
<!--          <p>-->
<!--            {{ posts[postId].text }}-->
<!--          </p>-->
<!--        </div>-->
<!--        &lt;!&ndash;          <a href="#" style="margin-left: auto;" class="link-unstyled" title="Make a change"><i class="fa fa-pencil"></i></a>&ndash;&gt;-->
<!--      </div>-->


<!--      <div class="post-date text-faded">-->
<!--        {{ posts[postId].publishedAt }}-->
<!--      </div>-->

<!--      &lt;!&ndash;        <div class="reactions">&ndash;&gt;-->
<!--      &lt;!&ndash;          <ul>&ndash;&gt;-->
<!--      &lt;!&ndash;            <li>💡</li>&ndash;&gt;-->
<!--      &lt;!&ndash;            <li>❤️</li>&ndash;&gt;-->
<!--      &lt;!&ndash;            <li>👎</li>&ndash;&gt;-->
<!--      &lt;!&ndash;            <li>👍</li>&ndash;&gt;-->
<!--      &lt;!&ndash;            <li>👌</li>&ndash;&gt;-->
<!--      &lt;!&ndash;          </ul>&ndash;&gt;-->
<!--      &lt;!&ndash;          <button class="btn-xsmall"><span class="emoji">❤️</span>️ 3</button>&ndash;&gt;-->
<!--      &lt;!&ndash;          <button class="btn-xsmall active-reaction"><span class="emoji">👌️</span>️ 1</button>&ndash;&gt;-->
<!--      &lt;!&ndash;          <button class="btn-xsmall">+ <i class="fa fa-smile-o emoji"></i></button>&ndash;&gt;-->
<!--      &lt;!&ndash;        </div>&ndash;&gt;-->

<!--    </div>-->
<!--  </div>-->
<!--</div>-->
<!--</div>-->

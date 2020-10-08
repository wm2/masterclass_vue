<template>
  <div class="post-list">
    <post-list-item
    v-for="post in posts"
    :post="post"
    :key="post['.key']"
    />
<!--    <div class="post-content">-->
<!--      <div>-->
<!--        <p>-->
<!--          {{ posts[postId].text }}-->
<!--        </p>-->
<!--      </div>-->
<!--      &lt;!&ndash;          <a href="#" style="margin-left: auto;" class="link-unstyled" title="Make a change"><i class="fa fa-pencil"></i></a>&ndash;&gt;-->
<!--    </div>-->



<!--    <div class="post-date text-faded">-->
<!--      {{ posts[postId].publishedAt }}-->
<!--    </div>-->
<!--    -->
    <!--        <div class="reactions">-->
    <!--          <ul>-->
    <!--            <li>💡</li>-->
    <!--            <li>❤️</li>-->
    <!--            <li>👎</li>-->
    <!--            <li>👍</li>-->
    <!--            <li>👌</li>-->
    <!--          </ul>-->
    <!--          <button class="btn-xsmall"><span class="emoji">❤️</span>️ 3</button>-->
    <!--          <button class="btn-xsmall active-reaction"><span class="emoji">👌️</span>️ 1</button>-->
    <!--          <button class="btn-xsmall">+ <i class="fa fa-smile-o emoji"></i></button>-->
    <!--        </div>-->
  </div>
</template>

<script>
import PostListItem from './PostListItem'
export default {
  name: 'PostList',
  components: {
    PostListItem
  },
  props: {
    posts: {
      required: true,
      type: Array
    }
  }
}
</script>

<style scoped>

</style>

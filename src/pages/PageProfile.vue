<template>
  <div class="flex-grid">

    <UserProfileCard v-if="!edit"
      :user="user"
      :user-posts-count="userPostsCount"
      :user-threads-count="userThreadCount"
    />

    <UserProfileCardEditor v-else
      :user="user"
      :user-posts-count="userPostsCount"
      :user-threads-count="userThreadCount"
    />

    <div class="col-7 push-top">

      <div class="profile-header">
                  <span class="text-lead">
                      {{ user.username }}'s recent activity
                  </span>
        <a href="#">See only started threads?</a>
      </div>

      <hr>

      <PostList :posts="userPosts" />

<!--      <div class="activity-list">-->
<!--        <div class="activity">-->
<!--          <div class="activity-header">-->
<!--            <img src="https://www.sideshowtoy.com/photo_9030371_thumb.jpg" alt="" class="hide-mobile avatar-small">-->
<!--            <p class="title">-->
<!--              How can I chop onions without crying?-->
<!--              <span>Joker started a topic in Cooking</span>-->
<!--            </p>-->

<!--          </div>-->

<!--          <div class="post-content">-->
<!--            <div>-->
<!--              <p>I absolutely love onions, but they hurt my eyes! Is there a way where you can chop onions without crying?</p>-->
<!--            </div>-->
<!--          </div>-->

<!--          <div class="thread-details">-->
<!--            <span>4 minutes ago</span>-->
<!--            <span>1 comments</span>-->
<!--          </div>-->
<!--        </div>-->





<!--      </div>-->
    </div>
  </div>
</template>

<script>
import PostList from '../components/PostList'
import {mapGetters} from 'vuex'
import {countObjectProperties} from '../utils'
import UserProfileCard from '../components/UserProfileCard'
import UserProfileCardEditor from '../components/UserProfileCardEditor'

export default {
  name: 'PageProfile',
  props: {
    edit: {
      type: Boolean,
      default: false
    }
  },
  components: {
    UserProfileCardEditor,
    UserProfileCard,
    PostList
  },
  computed: {
    ...mapGetters({
      user: 'authUser'
    }),
    userPostsCount () {
      return countObjectProperties(this.user.posts)
    },
    userThreadCount () {
      return countObjectProperties(this.user.threads)
    },
    userPosts () {
      if (this.user.posts) {
        return Object.values(this.$store.state.posts)
          .filter(post => post.userId === this.user['.key'])
      }
      return []
    }
  }
}
</script>

<style scoped>

</style>

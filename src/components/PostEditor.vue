<template>
  <form class="form-group" @submit.prevent="save">
      <textarea name=""
                id=""
                cols="30"
                rows="10"
                class="form-input"
                v-model="text"
      ></textarea>
    <div class="form-actions">
      <button class="btn-blue">Submit</button>
    </div>
  </form>
</template>

<script>
export default {
  name: 'PostEditor',
  props: {
    threadId: {
      required: true
    }
  },
  data () {
    return {
      text: ''
    }
  },
  methods: {
    save () {
      const post = {
        text: this.text,
        threadId: this.threadId
      }
      this.text = ''

      this.$emit('save', {post})  // {post: post, author: author} объект или не объект
      this.$store.dispatch('createPost', post)
    }
  }
}
</script>

<style scoped>

</style>

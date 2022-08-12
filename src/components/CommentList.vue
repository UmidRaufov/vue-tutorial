<template>
  <div v-if="comments.length > 0">
    <h3 class="text-center text-primary">Comments</h3>
    <comment-item
        class="w-75 mx-auto comment"
        v-for="comment in comments"
        v-bind:key="comment.id"
        :comment="comment"
        @remove="$emit('remove', comment)"
    />
  </div>
  <div v-else>
    <h3 class="text-center text-danger">No comments yet</h3>
  </div>
</template>

<script>
import CommentItem from './CommentItem';
export default {
  components: {
    CommentItem
  },
  props: {
    components: {
      CommentItem
    },
    comments: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.comment {
  border: 5px solid #ccc;
  padding: 10px;
  margin: 10px;
}
</style>
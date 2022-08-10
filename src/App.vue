<template>
  <div>
    <comment-form />
    <comment-list v-bind:comments="comments" />
  </div>
</template>

<script>
import CommentForm  from './components/CommentForm';
import CommentList  from './components/CommentList';

export default {
  components: {
    CommentForm,
    CommentList,
  },
  data() {
    return {
      comments: [
        {id: 1, name: "Jon  Smit", email: "1mail", content: "Lorem1"},
        {id: 2, name: "Karl Smit", email: "2mail", content: "Lorem2"},
        {id: 3, name: "Jeki Smit", email: "3mail", content: "Lorem3"},
        {id: 4, name: "Joan Smit", email: "3mail", content: "Lorem4"},
      ]
    }
  },
  methods: {
    increment() {
      this.count += 1
    },
    decrement() {
      this.count -= 1
    },
  }
}
</script>

<style scoped>

</style>
<template>
  <div>
    <div class="w-75 mx-auto">
      <h3>Add Comments</h3>
      <form @submit.prevent>
        <my-input
            v-model="comment.name"
            placeholder="Enter Your Name..."
            class="form-control"/>
        <my-input
            v-model="comment.email"
            placeholder="Enter Your Email..."
            class="form-control my-3"/>
        <my-input
            v-model="comment.body"
            placeholder="Enter Your Content..."
            class="form-control"/>
        <div class="d-flex flex-row-reverse">
          <my-button @click="createComment" class="btn btn-primary mt-3">Add Comment</my-button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton";
export default {
  components: {MyButton},
  data() {
    return {
      comment: {
        name: '',
        email: '',
        body: ''
      }
    }
  },
  methods: {
    createComment() {
      this.comment.id = Date.now();
      this.$emit('addComment', this.comment);
      this.comment = {
        name: '',
        email: '',
        body: ''
      }
    }
  }
}
</script>

<style>

</style>
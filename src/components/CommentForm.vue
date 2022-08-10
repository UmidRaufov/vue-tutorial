<template>
  <div>
    <div class="w-75 mx-auto">
      <h3>Add Comments</h3>
      <form @submit.prevent>
        <input
            v-model="comment.name"
            placeholder="Enter Your Name..."
            class="form-control"/>
        <input
            v-model="comment.email"
            placeholder="Enter Your Email..."
            class="form-control my-3"/>
        <input
            v-model="comment.content"
            placeholder="Enter Your Content..."
            class="form-control"/>
        <div class="d-flex flex-row-reverse">
          <button @click="createComment" class="btn btn-primary mt-3">Add Comment</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      comment: {
        name: '',
        email: '',
        content: ''
      }
    }
  }
}
</script>

<style>

</style>
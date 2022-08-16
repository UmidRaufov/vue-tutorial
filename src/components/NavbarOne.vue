<template>
  <div class="d-flex flex-column flex-md-row align-items-center pb-3 mb-4 border-bottom">
    <a href="/" class="d-flex align-items-center text-dark text-decoration-none">
      <svg xmlns="http://www.w3.org/2000/svg" width="40" height="32" class="me-2" viewBox="0 0 118 94" role="img"></svg>
      <span class="fs-4">Pricing example</span>
    </a>

    <nav class="d-inline-flex py-1 mt-2 mt-md-0 ms-md-auto">
      <my-button @click="showModal" class="py-2 m-2 btn btn-primary text-decoration-none">Add New Comment</my-button>
    </nav>
  </div>
</template>

<script>
export default {
  props: {
    showModal: {
      type: Function
    }
  },
  data() {
    return {
    }
  }
}
</script>
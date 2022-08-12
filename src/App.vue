<template>
  <navbar class="container" :showModal="showModal"/>
  <div>
    <my-modal v-model:show="modalVisible">
    <comment-form @addComment="createComment"/>
    </my-modal>
    <comment-list v-bind:comments="comments" @remove="removeComment"/>
  </div>
</template>

<script>
import CommentForm from './components/CommentForm';
import CommentList from './components/CommentList';
import Navbar from './components/FirstNavbar';
import MyModal from "@/components/MyModal";

export default {
  components: {
    MyModal,
    CommentForm,
    CommentList,
    Navbar,
  },
  data() {
    return {
      comments: [],
      modalVisible: false,
    }
  },
  methods: {
    createComment(comment) {
      this.comments.push(comment);
      this.modalVisible = false;
    },
    removeComment(comment) {
      this.comments.splice(this.comments.indexOf(comment), 1);
    },
    showModal(){
      this.modalVisible = true;
    },
  }
}
</script>

<style scoped>

</style>
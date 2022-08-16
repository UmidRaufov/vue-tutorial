<template>
  <navbar class="container" :showModal="showModal"/>
  <div>
    <my-modal v-model:show="modalVisible">
    <comment-form @addComment="createComment"/>
    </my-modal>
    <comment-list v-bind:comments="comments" @remove="removeComment" v-if="!isLoading"/>
    <div v-else class="spinner-grow col-md-3 offset-md-6" role="status">
      <span class="visually-hiden">Loading...</span>
    </div>
  </div>
</template>

<script>
import CommentForm from './components/CommentForm';
import CommentList from './components/CommentList';
import Navbar from './components/FirstNavbar';
import MyModal from "@/components/MyModal";
import axios from 'axios';

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
      isLoading: false,
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

    async fetchComments() {
      try{
        this.isLoading = true;
        const response = await axios.get('https://jsonplaceholder.typicode.com/comments?_limit=10');
        this.comments = response.data;
        this.isLoading = false;
      } catch(error) {
        alert('Something went wrong');
      }finally {
        this.isLoading = false;
      }
    }
    //Serverdan data olib keladi
  },
  mounted() {
    this.fetchComments();
  }
}
</script>

<style scoped>

</style>
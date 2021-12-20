<template>
  <div>
    <comment-form @addNewComment="addComment" />
    <comment-list :comments="comments" />
  </div>
</template>

<script>
import CommentList from "./components/CommentList.vue";
import CommentForm from "./components/CommentForm.vue";

export default {
  components: {
    CommentList,
    CommentForm,
  },
  data() {
    return {
      comments: [
        {
          id: 1,
          name: "Elbek",
          email: "elbek69114@gmail.com",
          content: "This is content",
        },
        {
          id: 2,
          name: "Elbek",
          email: "elbek69114@gmail.com",
          content: "This is content",
        },
      ],
    };
  },
  methods: {
    addComment(comment) {
      this.comments.push(comment);
    },
  },
};
</script>

<style>
.comment {
  border: 5px solid #ccc;
  padding: 10px;
  margin: 10px;
}
</style>
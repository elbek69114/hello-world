<template>
  <div>
    <div class="w-75 mx-auto">
      <h3>Add Comment</h3>
      <form @submit.prevent>
        <input
          type="text"
          placeholder="Enter your name"
          class="form-control"
          v-model="comment.name"
        />
        <input
          type="email"
          placeholder="Enter your email"
          class="form-control my-3"
          v-model="comment.email"
        />
        <input
          type="text"
          placeholder="Enter your content"
          class="form-control"
          v-model="comment.content"
        />
        <div class="d-flex flex-row-reverse">
          <button class="btn btn-primary mt-3" @click="addComment">
            Add comment
          </button>
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
        name: "",
        email: "",
        content: "",
      },
    };
  },

  methods: {
    addComment() {
      this.comment.id = Date.now();
      this.$emit("addNewComment", this.comment);
      this.comment = {
        name: "",
        email: "",
        content: "",
      };
    },
  },
};
</script>

<style scoped>
</style>
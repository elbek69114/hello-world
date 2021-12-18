<template>
  <div>
    <div class="w-75 mx-auto">
      <h3>Add Comment</h3>
      <form @submit.prevent>
        <input
          type="text"
          placeholder="Enter your name"
          class="form-control"
          :value="name"
          @input="name = $event.target.value"
        />
        <input
          type="email"
          placeholder="Enter your email"
          class="form-control my-3"
          :value="email"
          @input="email = $event.target.value"
        />
        <input
          type="text"
          placeholder="Enter your content"
          class="form-control"
          :value="content"
          @input="content = $event.target.value"
        />
        <div class="d-flex flex-row-reverse">
          <button class="btn btn-primary mt-3" @click="addComment">
            Add comment
          </button>
        </div>
      </form>
    </div>
    <div
      class="w-75 mx-auto comment"
      v-for="comment in comments"
      v-bind:key="comment.id"
    >
      <div><b>Name:</b>{{ comment.name }}</div>
      <div><b>Email:</b>{{ comment.email }}</div>
      <div><b>Content:</b>{{ comment.content }}</div>
    </div>
  </div>
</template>

<script>
export default {
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
      name: "",
      email: "",
      content: "",
    };
  },
  methods: {
    addComment() {
      const newComment = {
        id: this.comments.length + 1,
        name: this.name,
        email: this.email,
        content: this.content,
      };
      this.comments.push(newComment);
      this.name = "";
      this.email = "";
      this.content = "";
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
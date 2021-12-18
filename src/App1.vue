<template>
  <div>
    <h1>Hello world</h1>
    <h2>
      Count: <strong>{{ count }}</strong>
    </h2>
    <button class="btn btn-success" v-on:click="increment">Inrement</button>
    <button class="btn btn-primary" v-on:click="decrement">Decrement</button>
    <div class="comment">
      <div><b>Name:</b> Elbek Bozorov</div>
      <div><b>Email:</b>elbek69114@gmail.com</div>
      <div><b>Content:</b>This is content</div>
    </div>
    <div class="comment" v-for="comment in comments" v-bind:key="comment.id">
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
      message: "Hello vue",
      count: 0,
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
    increment() {
      this.count++;
    },
    decrement() {
      this.count--;
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
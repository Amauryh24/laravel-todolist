<template>
  <div>
    <h1 class="title-index-c">Posts</h1>

    <div class="row">
      <div class="col-md-10"></div>

      <div class="col-md-2">
        <router-link :to="{ name: 'create' }" class="btn btn-primary">Create</router-link>
      </div>
    </div>
    <br />

    <div class="card" style="width: 18rem;" v-for="post in posts" :key="post.id">
      <div class="card-body">
        <h2 class="card-title">{{ post.title }}</h2>

        <h6 class="card-subtitle mb-2 text-muted">Id: {{ post.id }}</h6>

        <p class="card-text">Description : {{ post.body }}</p>

        <router-link :to="{name: 'edit', params: { id: post.id }}" class="btn btn-primary">Edit</router-link>

        <button class="btn btn-danger" @click.prevent="deletePost(post.id)">Delete</button>
      </div>
    </div>
  </div>
</template>

  

<script>
export default {
  data() {
    return {
      posts: []
    };
  },

  created() {
    let uri = "/api/posts";

    this.axios.get(uri).then(response => {
      this.posts = response.data.data;

      console.log(this.posts);

      console.log("prout");
    });
  },

  methods: {
    deletePost(id) {
      let uri = `/api/post/delete/${id}`;

      this.axios.delete(uri).then(response => {
        this.posts.splice(this.posts.indexOf(id), 1);
      });
    }
  }
};
</script>
<style >
body {
  background: linear-gradient(
    157deg,
    rgba(77, 184, 128, 1) 0%,
    rgba(69, 145, 116, 1) 52%,
    rgba(53, 73, 94, 1) 100%
  );
  background-repeat: no-repeat;
  background-size: cover;
  padding-bottom: 378px;
}

.title-index-c {
  text-align: center;
  font-size: 3rem;
  padding-top: 4rem;
  color: orange;
}
</style>
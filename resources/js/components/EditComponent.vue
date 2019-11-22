<template>
  <div>
    <h1 class="title-edit-c">Edit Post</h1>

    <div class="bloc-edit-c">
      <form @submit.prevent="updatePost">
        <div class="row">
          <div class="col-md-6">
            <div class="form-group">
              <label class="post-edit-c">Post Title:</label>

              <input type="text" class="form-control" v-model="post.title" />
            </div>
          </div>
        </div>

        <div class="row">
          <div class="col-md-6">
            <div class="form-group">
              <label class="post-edit-c">Post Body:</label>

              <textarea class="form-control" v-model="post.body" rows="5"></textarea>
            </div>
          </div>
        </div>
        <br />

        <div class="form-group">
          <button class="btn btn-primary">Update</button>
        </div>
      </form>
    </div>
  </div>
</template>

  

<script>
export default {
  data() {
    return {
      post: {}
    };
  },

  created() {
    let uri = `/api/post/edit/${this.$route.params.id}`;

    this.axios.get(uri).then(response => {
      this.post = response.data;
    });
  },

  methods: {
    updatePost() {
      let uri = `/api/post/update/${this.$route.params.id}`;

      this.axios.post(uri, this.post).then(response => {
        this.$router.push({ name: "posts" });
      });
    }
  }
};
</script>
<style>
.title-edit-c {
  text-align: center;
  font-size: 3rem;
  padding-top: 4rem;
  color: orange;
}
.bloc-edit-c {
  width: 80%;
  margin-left: 31%;
}
.post-edit-c {
  color: orange;
  font-size: 30px;
  margin-top: 1rem;
}
</style>

<template>
  <div>
    <h1 class="title-create-c">Create A New Todo!</h1>

    <div class="form-bloc-c">
      <form @submit.prevent="addPost">
        <div class="row">
          <div class="col-md-6 bloc-title-c">
            <div class="form-group">
              <label class="post-title-c">Post Title:</label>

              <input type="text" class="form-control" v-model="post.title" />
            </div>
          </div>
        </div>

        <div class="row">
          <div class="col-md-6">
            <div class="form-group">
              <label class="post-body-c">Post Body:</label>

              <textarea class="form-control" v-model="post.body" rows="5"></textarea>
            </div>
          </div>
        </div>
        <br />

        <div class="form-group">
          <button class="btn btn-primary btn-create-c">Create</button>
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

  methods: {
    addPost() {
      let uri = "/api/post/create";

      this.axios.post(uri, this.post).then(response => {
        this.$router
          .push({ name: "posts" })

          .catch(error => {
            console.log("shit happen");
          });
      });
    }
  }
};
</script>
<style>
.title-create-c {
  text-align: center;
  font-size: 3rem;
  padding-top: 4rem;
  color: orange;
}

.post-title-c {
  color: orange;
  font-size: 30px;
  margin-top: 1rem;
}
.post-body-c {
  color: orange;
  font-size: 30px;
}
.form-bloc-c {
  width: 80%;
  margin-left: 31%;
}
.btn-create-c {
  background-color: orange;
  text-transform: uppercase;
  letter-spacing: 1px;
  margin-left: 18%;
  box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.425);
}
</style>
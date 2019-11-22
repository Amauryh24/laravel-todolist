<template>
  <div class="row justify-content-center">
    <div class="col-md-8">
      <div class="card card-default">
        <div class="card-body">
          <h1 class="title">Hey, welcome in todo App</h1>
          <div class="subtitle">
            <br />Yes we can !
            <br />Create / Rename / Update / Delete
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

  

<script>
export default {
  mounted() {
    console.log("Component mounted.");
  }
};
</script>
<style>
.title {
  text-align: center;
}
.subtitle {
  text-align: center;
}
.card-body {
  padding-top: 10rem;
}
</style>
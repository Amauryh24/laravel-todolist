<template>
  <div class="row justify-content-center">
    <div class="col-md-8 home-c">
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
  font-size: 3rem;
  font-weight: 900;
}
.subtitle {
  text-align: center;
  font-size: 2rem;
  text-transform: uppercase;
}
.home-c {
  padding-top: 10rem;
}
.card-default {
  border-radius: 25px;
  background-color: whitesmoke;
  color: rgba(69, 145, 116, 1);
  box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.425);
}
</style>
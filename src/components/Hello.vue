<template>
  <div class="hello-message">
    <h1>Hello, welcome to our application!</h1>
  </div>
</template>

// No use for this at the moment in my opinion, but might be useful if I ever
plan on intergrating this with Snow robot!

<script>
export default {
  name: "Hello-there",
};
</script>

<style scoped>
.hello-message {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  height: 100vh;
  padding-top: 20px;
  background-color: #f3f3f3;
}

.hello-message h1 {
  color: #3498db;
  font-size: 28px;
  margin: 0;
}
</style>

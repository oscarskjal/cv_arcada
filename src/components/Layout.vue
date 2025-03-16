<template>
  <div class="layout">
    <h1>Building Layout</h1>
    <div class="floor">
      <h2>Floor 1</h2>
      <p>Entry, Coat hanging area</p>
    </div>
    <div class="floor">
      <h2>Floor 2</h2>
      <p>Cafeteria, Large auditorium, Small auditorium, Library, Infopoint</p>
    </div>
    <div class="floor">
      <h2>Floor 3</h2>
      <p>IT lab, Computer lounge, Classrooms</p>
    </div>
    <div class="floor">
      <h2>Floor 4</h2>
      <p>Nursing student rooms, Classrooms</p>
    </div>
    <div class="floor">
      <h2>Floor 5</h2>
      <p>Classrooms</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "LayOut",
};
</script>

<style scoped>
.layout {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  max-width: 800px;
  margin: 20px auto;
  font-family: Arial, sans-serif;
}

.layout h1 {
  color: #b86cf6;
  font-size: 28px;
  margin-bottom: 20px;
}

.floor {
  margin-bottom: 20px;
}

.floor h2 {
  color: #e59a10;
  font-size: 24px;
  margin-bottom: 10px;
}

.floor p {
  color: #333333;
  font-size: 18px;
  line-height: 1.6;
}
</style>

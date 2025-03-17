<template>
  <div class="robot-face">
    <div class="robot-head">
      <div class="robot-eyes">
        <div class="robot-eye left-eye"></div>
        <div class="robot-eye right-eye"></div>
      </div>
      <div class="robot-mouth"></div>
    </div>
  </div>
</template>

// No use for this at the moment in my opinion, but might be useful if I ever
plan on intergrating this with Snow robot!

<script>
export default {
  name: "Robot-face",
};
</script>

<style scoped>
.robot-face {
  position: absolute;
  top: 10px;
  left: 10px;
}

.robot-head {
  width: 60px;
  height: 60px;
  background-color: #3498db;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

.robot-eyes {
  display: flex;
  justify-content: space-between;
  width: 80%;
}

.robot-eye {
  width: 12px;
  height: 12px;
  background-color: white;
  border-radius: 50%;
}

.robot-mouth {
  width: 30px;
  height: 6px;
  background-color: white;
  border-radius: 3px;
  margin-top: 5px;
}
</style>

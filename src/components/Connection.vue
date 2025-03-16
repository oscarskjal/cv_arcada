<template>
  <div class="connection" :class="{ connected: isConnected }"></div>
</template>

<script>
export default {
  name: "ConnecTion",
  props: {
    isConnected: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style scoped>
.connection {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background-color: red;
  position: absolute;
  top: 10px;
  left: 10px;
}

.connection.connected {
  background-color: green;
}
</style>

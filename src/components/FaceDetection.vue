<template>
  <div class="face-detection">
    <Connection :isConnected="faces.length > 0" />
    <h1>Face Detection</h1>
    <div v-if="faces.length > 0">
      <h2>Detected Faces:</h2>
      <ul>
        <li v-for="(face, index) in faces" :key="index">
          Face {{ index + 1 }}: (x: {{ face.x }}, y: {{ face.y }}, width:
          {{ face.width }}, height: {{ face.height }})
        </li>
      </ul>
    </div>
    <div v-else>
      <p>No faces detected.</p>
    </div>
  </div>
</template>

<script>
import { io } from "socket.io-client";
import Connection from "./Connection.vue";

export default {
  name: "FaceDetection",
  components: {
    Connection,
  },
  data() {
    return {
      faces: [],
      socket: null,
    };
  },
  mounted() {
    this.socket = io("http://localhost:5000", {
      transports: ["websocket", "polling"],
    });

    this.socket.on("faces_detected", (data) => {
      this.faces = data.faces || [];
      this.$emit("facesDetected", this.faces.length > 0);
    });
  },
  beforeUnmount() {
    if (this.socket) {
      this.socket.disconnect();
    }
  },
};
</script>

<style scoped>
.face-detection {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  max-width: 800px;
  margin: 20px auto;
  font-family: Arial, sans-serif;
  position: relative;
}

.face-detection h1 {
  color: #3498db;
  font-size: 28px;
  margin-bottom: 20px;
}

.face-detection ul {
  list-style-type: none;
  padding: 0;
}

.face-detection li {
  background-color: #f3f3f3;
  padding: 10px;
  margin-bottom: 10px;
  border-radius: 5px;
}
</style>

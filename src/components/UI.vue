<template>
  <div class="container">
    <div class="content">
      <div class="button-grid">
        <div class="button-container">
          <button class="button blue" @click="showAboutUs">About Us</button>
        </div>
        <div class="button-container">
          <button class="button red" @click="showLayout">Layout</button>
        </div>
        <div class="button-container">
          <button class="button green" @click="showWhoAreYou">
            Who Are You?
          </button>
        </div>
        <div class="button-container">
          <button class="button yellow" @click="showFaceDetection">
            Face Detection
          </button>
        </div>
      </div>
      <div class="text-content">
        <AboutUs v-if="isAboutUsVisible" />
        <Layout v-if="isLayoutVisible" />
        <WhoAreYou v-if="isWhoAreYouVisible" />
        <FaceDetection
          v-if="isFaceDetectionVisible"
          @facesDetected="handleFaceDetected"
        />
      </div>
    </div>
  </div>
</template>

<script>
import AboutUs from "./AboutUs.vue";
import Layout from "./Layout.vue";
import WhoAreYou from "./WhoAreYou.vue";
import FaceDetection from "./FaceDetection.vue";

export default {
  name: "UI",
  components: {
    AboutUs,
    Layout,
    WhoAreYou,
    FaceDetection,
  },
  data() {
    return {
      isAboutUsVisible: false,
      isLayoutVisible: false,
      isWhoAreYouVisible: false,
      isFaceDetectionVisible: false,
    };
  },
  methods: {
    showAboutUs() {
      this.isAboutUsVisible = true;
      this.isLayoutVisible = false;
      this.isWhoAreYouVisible = false;
      this.isFaceDetectionVisible = false;
    },
    showLayout() {
      this.isLayoutVisible = true;
      this.isAboutUsVisible = false;
      this.isWhoAreYouVisible = false;
      this.isFaceDetectionVisible = false;
    },
    showWhoAreYou() {
      this.isWhoAreYouVisible = true;
      this.isAboutUsVisible = false;
      this.isLayoutVisible = false;
      this.isFaceDetectionVisible = false;
    },
    showFaceDetection() {
      this.isFaceDetectionVisible = true;
      this.isAboutUsVisible = false;
      this.isLayoutVisible = false;
      this.isWhoAreYouVisible = false;
    },
    handleFaceDetected() {
      console.log("Face detected, backend handles the response.");
    },
  },
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-color: #f3f3f3;
  position: relative;
}

.content {
  display: flex;
  align-items: flex-start;
}

.button-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  padding: 20px;
  background: white;
  border-radius: 10px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

.button-container {
  display: flex;
  align-items: center;
}

.button {
  width: 150px;
  height: 150px;
  font-size: 22px;
  color: white;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  transition: background 0.3s;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
}

.speak-button {
  background: none;
  border: none;
  font-size: 24px;
  cursor: pointer;
  margin-left: 10px;
}

.text-content {
  margin-left: 20px;
}

.blue {
  background-color: #3498db;
}
.blue:hover {
  background-color: #2980b9;
}

.red {
  background-color: #e74c3c;
}
.red:hover {
  background-color: #c0392b;
}
.green {
  background-color: #2ecc71;
}
.green:hover {
  background-color: #27ae60;
}

.yellow {
  background-color: #f1c40f;
  color: black;
}
.yellow:hover {
  background-color: #d4ac0d;
}

.robot-text {
  margin-top: 10px;
  font-size: 18px;
  color: #3498db;
  text-align: center;
}
</style>

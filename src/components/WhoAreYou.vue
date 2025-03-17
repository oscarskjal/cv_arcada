<template>
  <div class="who-are-you">
    <h1>What am I?</h1>
    <p>
      This is an innovative application that leverages the power of OpenCV to
      enhance user experience. This app integrates computer vision techniques to
      provide seamless and intuitive interactions.
    </p>
    <p>
      By utilizing OpenCV, the app is able to offer features such as real-time
      image processing, object detection, and facial recognition. The goal is to
      create smart solutions that make everyday tasks more efficient, while also
      providing a fun and engaging user experience.
    </p>
    <button @click="speakText">🔊 Speak</button>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "WhoAreYou",
  methods: {
    async speakText() {
      const text = `We are an innovative application that leverages the power of OpenCV to enhance user experience. Our app integrates advanced computer vision techniques to provide seamless and intuitive interactions. By utilizing OpenCV, we are able to offer features such as real-time image processing, object detection, and facial recognition. Our goal is to create smart solutions that make everyday tasks easier and more efficient, while also providing a fun and engaging user experience.`;
      try {
        const response = await axios.post(
          "http://localhost:5000/text_to_speech",
          { text }
        );
        console.log(response.data.message);
      } catch (error) {
        console.error("Error speaking text:", error);
      }
    },
  },
};
</script>

<style scoped>
.who-are-you {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  max-width: 800px;
  margin: 20px auto;
  font-family: Arial, sans-serif;
}

.who-are-you h1 {
  color: #2ecc71;
  font-size: 28px;
  margin-bottom: 10px;
}

.who-are-you p {
  color: #333333;
  font-size: 18px;
  line-height: 1.6;
  margin-bottom: 10px;
}

.who-are-you button {
  background-color: #2ecc72;
  color: white;
  border: none;
  border-radius: 10px;
  padding: 10px 20px;
  cursor: pointer;
  font-size: 18px;
  transition: background 0.3s;
}

.who-are-you button:hover {
  background-color: #0f85b8;
}
</style>

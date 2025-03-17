<template>
  <div class="about-us">
    <h1>About Arcada</h1>
    <p>
      Arcada is a multi-professional University of Applied Sciences in Finland.
      At our campus in Helsinki (Finland), our 2,700 students and 170 staff work
      across disciplines to advance culture and knowledge.
    </p>
    <p>
      At Arcada, high-level research with societal impact meets lifelong
      learning within all our areas of expertise: Business management and
      analytics, Energy and materials technology, Health and welfare, Culture
      and media, and Healthcare. Together with our partners, we are building
      Nordic bridges to be globally relevant. We create smart solutions for a
      dynamic working life and a vibrant Swedish-speaking culture.
    </p>
    <button @click="speakText">🔊 Speak</button>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "AboutUs",
  methods: {
    async speakText() {
      const text = `Arcada is a multi-professional University of Applied Sciences in Finland. At our campus in Helsinki (Finland), our 2,700 students and 170 staff work across disciplines to advance culture and knowledge. At Arcada, high-level research with societal impact meets lifelong learning within all our areas of expertise: Business management and analytics, Energy and materials technology, Health and welfare, Culture and media, and Healthcare. Together with our partners, we are building Nordic bridges to be globally relevant. We create smart solutions for a dynamic working life and a vibrant Swedish-speaking culture.`;
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
.about-us {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  max-width: 800px;
  margin: 20px auto;
  font-family: Arial, sans-serif;
}

.about-us h1 {
  color: #3498db;
  font-size: 28px;
  margin-bottom: 10px;
}

.about-us p {
  color: #333333;
  font-size: 18px;
  line-height: 1.6;
  margin-bottom: 10px;
}

.about-us button {
  background-color: #2e85cc;
  color: white;
  border: none;
  border-radius: 10px;
  padding: 10px 20px;
  cursor: pointer;
  font-size: 18px;
  transition: background 0.3s;
}

.about-us button:hover {
  background-color: #27ae60;
}
</style>

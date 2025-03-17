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
    <button @click="speakText">🔊 Speak</button>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "LayOut",
  methods: {
    async speakText() {
      const text = `Building Layout: Floor 1: Entry, Coat hanging area. Floor 2: Cafeteria, Large auditorium, Small auditorium, Library, Infopoint. Floor 3: IT lab, Computer lounge, Classrooms. Floor 4: Nursing student rooms, Classrooms. Floor 5: Classrooms.`;
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
  color: #e08529;
  font-size: 28px;
  margin-bottom: 20px;
}

.floor {
  margin-bottom: 20px;
}

.floor h2 {
  color: #c04417;
  font-size: 24px;
  margin-bottom: 10px;
}

.floor p {
  color: #333333;
  font-size: 18px;
  line-height: 1.6;
}

.layout button {
  background-color: #dd720e;
  color: white;
  border: none;
  border-radius: 10px;
  padding: 10px 20px;
  cursor: pointer;
  font-size: 18px;
  transition: background 0.3s;
}

.layout button:hover {
  background-color: #f0190a;
}
</style>

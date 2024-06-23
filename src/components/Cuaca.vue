<template>
  <div class="weather-widget">
    <h2>Widget Cuaca</h2>
    <div class="search-bar">
      <input v-model="city" placeholder="Enter city name" @keyup.enter="getWeather" />
      <button @click="getWeather">Search</button>
    </div>
    <div v-if="weather" class="weather-info">
      <div class="weather-item weather-location">
        <img src="../assets/loc.png" alt="location icon" />
        <p><strong>Location:</strong><br>{{ weather.name }}</p>
      </div>
      <div class="weather-item weather-temp">
        <img src="../assets/temp.png" alt="temperature icon" />
        <p><strong>Temperature:</strong><br>{{ weather.main.temp }}°C</p>
      </div>
      <div class="weather-item weather-description">
        <img :src="`http://openweathermap.org/img/wn/${weather.weather[0].icon}.png`" alt="weather icon" />
        <p><strong>Weather:</strong><br>{{ weather.weather[0].description }}</p>
      </div>
    </div>
    <div v-else>
      <p>Enter a city name to see the weather.</p>
    </div>
  </div>
  <footer>
    <a href="https://github.com/Aldiansyah239">
      <p>&copy; Aldi Kuncruk</p>
    </a>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
import axios from 'axios'

const city = ref('')
const weather = ref(null)

const getWeather = async () => {
  const apiKey = '23f0987b01236b80c30ceeb06f7c8c22'
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city.value}&units=metric&appid=${apiKey}`

  try {
    const response = await axios.get(url)
    weather.value = response.data
  } catch (error) {
    console.error(error)
    weather.value = null
  }
}
</script>

<style scoped>
.weather-widget {
  padding: 20px;
  border: 2px dotted var(--lightest-gray);
  border-radius: 10px;
  max-width: 550px;
  margin: 50px auto;
  text-align: center;
  background-color: var(--medium-gray);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.weather-widget h2 {
  color: var(--lightest-gray);
  font-size: 36px;
  font-weight: bold;
  margin-bottom: 20px;
}

.weather-widget p {
  color: var(--lightest-gray);
}

.search-bar {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}

.search-bar input {
  padding: 10px;
  width: 70%;
  margin-right: 10px;
  border: 1px solid var(--lightest-gray);
  border-radius: 5px;
  background-color: var(--lightest-gray);
}

.search-bar button {
  padding: 10px;
  border: 1px dotted var(--lightest-gray);
  background-color: var(--medium-gray);
  color: var(--lightest-gray);
  cursor: pointer;
  border-radius: 5px;
}

.search-bar button:hover {
  background-color: var(--dark-gray);
}

.weather-info {
  margin-top: 20px;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.weather-item {
  margin: 10px;
  border: 1px solid whitesmoke;
  border-radius: 5px;
  padding: 10px;
  flex: 1;
  background-color: var(--light-gray);
  text-align: center;
  width: 200px;
}

.weather-item img {
  margin-top: 10px;
  width: 35px;
  height: 35px;
}

.weather-item p {
  margin: 0;
  color: var(--lightest-gray);
}

.weather-border {
  border-top: 1px solid var(--lightest-gray);
  margin-top: 10px;
  padding-top: 10px;
}

.weather-location {
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
}

.weather-temp {
  border-radius: 0;
}

.weather-description {
  border-top-left-radius: 0;
  border-top-right-radius: 0;
}

footer {
  color: var(--lightest-gray);
  border: 2px dotted var(--lightest-gray);
  width: 200px;
  border-radius: 10px;
  margin: 20px auto;
  cursor: pointer;
}

footer a {
  color: var(--lightest-gray);
}

footer p {
  margin-top: 15px;
  font-weight: bold;
}
</style>

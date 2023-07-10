<template>
    <div class="weather-widget">
      <h2 class="widget-title">Pencarian Cuaca</h2>
      <div class="location-input">
        <label for="location">Masukan Lokasi:</label>
        <input type="text" id="location" v-model="location" />
        <button @click="fetchWeatherData">Cari Cuaca</button>
      </div>
      <div v-if="weatherData" class="weather-data">
        <p class="location">Location: {{ weatherData.name }}</p>
        <p v-if="weatherData.main" class="temperature">
          Temperature/Suhu: {{ weatherData.main.temp }}°C
        </p>
        <p v-if="weatherData.weather" class="description">
          Description: {{ weatherData.weather[0].description }}
        </p>
      </div>
      <p v-else>Loading weather data...</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        location: '',
        weatherData: null
      };
    },
    methods: {
      async fetchWeatherData() {
        try {
          const apiKey = 'b7bfca7b27a3485144fea086c50d09dc';
          const apiUrl = `https://api.openweathermap.org/data/2.5/weather?q=${this.location}&appid=${apiKey}`;
  
          const response = await fetch(apiUrl);
          const data = await response.json();
  
          this.weatherData = data;
        } catch (error) {
          console.error('Error fetching weather data:', error);
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .weather-widget {
    border: 1px solid #7989d1;
    padding: 20px;
    margin-bottom: 20px;
    text-align: center;
    background-color: #4a924e;
  }
  
  .widget-title {
    margin-top: 0;
    color: #c8fa13;
  }
  
  .location-input {
    margin-bottom: 10px;
  }
  
  .weather-data {
    margin-top: 10px;
  }
  div{
    background-image: url();
  }
  .location {
    font-size: 18px;
    font-weight: bold;
  }
  
  .temperature {
    font-size: 24px;
    color: #ff5722;
  }
  
  .description {
    font-size: 16px;
  }
  </style>
  
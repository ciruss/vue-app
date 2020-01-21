<template>
  <div class="container" id="app">
    <h1>App</h1>
    <search @searchResult="searchResult" />
    <weather-table v-if="Object.keys(weatherInfo).length > 0" :weatherInfo="weatherInfo" />
  </div>
</template>

<script>
import Search from "@/components/Search";
import WeatherTable from "@/components/WeatherTable";

export default {
  name: "app",
  components: {
    Search,
    WeatherTable
  },
  data() {
    return {
      weatherInfo: {}
    };
  },
  methods: {
    searchResult(data) {
      this.weatherInfo = data;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

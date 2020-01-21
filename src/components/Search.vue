<template>
  <div>
    <form @submit.prevent="submitSearch">
      <input v-model="searchInput" type="text" placeholder="Search city" />
      <button :disabled="this.searchInput === ''">Search</button>
    </form>
  </div>
</template>

<script>
const apiKey = process.env.VUE_APP_WEATHER_API;

export default {
  name: "search",
  data() {
    return {
      searchInput: ""
    };
  },
  methods: {
    submitSearch() {
      fetch(
        `http://api.openweathermap.org/data/2.5/weather?q=${this.searchInput}&units=metric&appid=${apiKey}`
      ).then(res => res.json().then(data => this.$emit("searchResult", data)));

      this.searchInput = "";
    }
  }
};
</script>

<style scoped>
button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
</style>
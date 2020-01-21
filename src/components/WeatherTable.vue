<template>
  <table>
    <thead>
      <tr>
        <th colspan="2">{{ weatherInfo.name }}</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Temp:</td>
        <td>{{ weatherInfo.main.temp }}</td>
      </tr>
      <tr>
        <td>Feels like:</td>
        <td>{{ weatherInfo.main.feels_like }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: "weather-table",
  props: {
    weatherInfo: Object
  }
};
</script>

<style scoped>
th {
  text-align: center;
}
</style>
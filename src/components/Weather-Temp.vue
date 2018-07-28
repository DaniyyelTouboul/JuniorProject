<template>
    <div class="WeatherTemp">
    <div class="blue lighten-2 temp-cont">
        <h3>Leipzig</h3>

    <div class="row">
        <span class="col s6 semi-header">Temperature</span>
        <span class="col s6 semi-header">Value</span>
    </div>
    <div class="row">
        <span class="col s6 semi-header">Windspeed</span>
        <span class="col s6 semi-header">Value</span>
    </div>
        <div class="row">
        <span class="col s6 semi-header">Humidity</span>
        <span class="col s6 semi-header">Value</span>
    </div>
</div>
    </div>
</template>


<script>
export default {
  name: "WeatherTemp"
};
</script>


<style scoped>
.temp-cont {
  margin: 0 auto;
  width: 20%;
  border-style: solid;
  border-width: 2px;
  border-color: #2196f3;
}
.semi-header {
  font-size: 15px;
}
</style>


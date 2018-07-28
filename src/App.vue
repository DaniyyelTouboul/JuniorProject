<template>
  <div id="app">
    <InputPart/>
    <WeatherTemp/>
  </div>
</template>

<script>
import WeatherTemp from "./components/Weather-Temp";
import InputPart from "./components/Input-Part";

export default {
  name: "App",
  components: {
    WeatherTemp,
    InputPart
  },
  data() {
    return {
      showWeather: false,
    };
  },
  methods: {
    showWeather: function(updatedWeaterState){
      this.showWeather = updatedWeaterState;
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

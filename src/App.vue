<template>
  <div id="app">
    <InputPart/>
    <WeatherTemp v-if="showWeather"/>
    <NothingHasFound v-if="showError" v-on:nothingToShow="updateErrorMessage($event)"/>
    <Test1> </Test1>
     <h3 @changeTitle="updateTitle($event)"> {{ test_title}} </h3>
  </div>
</template>

<script>
import WeatherTemp from "./components/Weather-Temp";
import InputPart from "./components/Input-Part";
import NothingHasFound from "./components/Nothing-Has-Found";

export default {
  name: "App",
  components: {
    WeatherTemp,
    InputPart,
    NothingHasFound,
  },
  data() {
    return {
      test_title: "Test 2",
      showWeather: false,
      showError: false
    };
  },
  methods: {
    updateTitle: function(updatedTitle) {
      this.test_title = updatedTitle;
    },
    updateErrorMessage: function(updatedErrorState) {
      this.showWeather = updatedErrorState;
    },
    showWeatherState: function(updatedWeaterState) {
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

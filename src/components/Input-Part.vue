
<template>
    <div class="InputPart">
          <div class="temp-cont">
<span class="into-header">Whats the weather in? </span>
    <input type="text" v-model="city_name" @change="getWeather" placeholder="Enter city name"> 
    <div class="row">
        <span class="col s6" id="city_name_link">City Name</span>
                <span class="col s6" id="zip_code_link">Zip</span>
    </div>
        </div>
    </div>

</template>


<script>
import App from "./App";

export default {
  name: "InputPart",
  data() {
    return {
      city_name: "",
      temperature: "",
      humidity: "",
      windspeed: "",

      weathers: [
        {
          temp: "30c",
          humidity: "80%",
          windspeed: "100km"
        },
        {
          temp: "30c",
          humidity: "80%",
          windspeed: "100km"
        },
        {
          temp: "30c",
          humidity: "80%",
          windspeed: "100km"
        }
      ]
    };
  },
  methods: {
    getWeather: function() {
      this.$http
        .get(
          "http://api.openweathermap.org/data/2.5/forecast?q=" +
            this.city_name +
            ",de&units=metric&appid=fcadd28326c90c3262054e0e6ca599cd"
        )
        .then(function(response) {
          if (response.ok == false) {
            this.$emit("showWeather", false);
            // show other copomemnt
          } else {
            console.log(response.body.list);
          }

          //   console.log(App.data().showWeather);
        });
    }
  }
};
</script>


<style scoped>
.temp-cont {
  margin: 0 auto;
  width: 20%;
}
.into-header {
  font-size: 25px;
  font-weight: bold;
}
#city_name_link {
  font-weight: bold;
}
#zip_code_link {
}
</style>


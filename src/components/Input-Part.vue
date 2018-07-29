
<template>
    <div class="InputPart">
          <div class="temp-cont">
<span class="into-header" @click="callBack"> {{ header_title}} </span>
    <input type="text" v-model="city_name" @change="getWeather" placeholder="Enter city name"> 
    <div class="row"> 
        <span class="col s6" id="city_name_link">City Name</span>
                <span class="col s6" id="zip_code_link">Zip</span>
    </div>
        </div>
    </div>

</template>

<script>
export default {
  name: "InputPart",
  data() {
    return {
      header_title: "Whats the weather in?",
      city_name: "",
      temperature: "",
      humidity: "",
      windspeed: "",

      weathers: [
        {
          temp: "90c",
          humidity: "30%",
          windspeed: "140kmh"
        },
        {
          temp: "30c",
          humidity: "80%",
          windspeed: "100kmh"
        },
        {
          temp: "35c",
          humidity: "11`%",
          windspeed: "100kmh"
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
            //show error.
            this.$emit("nothingToShow", true);
            // show other copomemnt
          } else {
            // show weather.
            console.log(response.body.list);
          }

          //   console.log(App.data().showWeather);
        });
    },
    callBack: function() {
      this.header_title = "Just a prank Bro!";
      this.$emit("changeTitle", "Just a prank Bro!");
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


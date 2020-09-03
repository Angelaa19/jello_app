<template>
  <div class="home">
    <h1 id="demo">New Location</h1>
      <button v-on:click="getCurrentPosition()">Try It</button>
      <h2 id="showLocation">You are here!</h2>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      location: [],
      newLatitude: "",
      newLongitude: "",
      newTimestamp: "",    
    };
  },
  created: function() {
    // this.indexLocations();
    var x = document.getElementById("demo");
  },
  methods: {
    getPosition: function(position) {
    },
    getCurrentPosition: function() {
      console.log("Hello");
      if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(this.showPosition);
      // eslint-disable-next-line no-empty
      }
    },
    showPosition: function(position) {
      var params = {
        latitude: position.coords.latitude,
        longitude: position.coords.longitude,
        timestamp: position.timestamp,
      };
      console.log(position.coords.latitude);
      console.log(position.coords.longitude);
      console.log(position.timestamp);
      axios.post("api/twilio/voice", params)
        .then(response => {});
    },
  },
};
</script>
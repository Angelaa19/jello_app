<template>
  <div class="home">
    <br>
      <!-- Main -->
					<div id="main">

						<!-- Introduction -->
							<section id="intro" class="main">
								<div class="spotlight">
									<div class="content">
										<header class="major">
											<h2 style="text-align:left;">You are not alone</h2>
										</header>
										<p>On average, 24 people per minute are victims of rape, physical violence or stalking by an intimate partner in the United States — more than 12 million women and men over the course of a year.[i]</p>
										<ul class="actions">
											<li><a href="generic.html" class="button">Learn More</a></li>
										</ul>
									</div>
									<span class="image"><img src="https://i.pinimg.com/564x/87/f3/62/87f3625d19b744c9fa92af84a7546161.jpg" alt="girl with umbrella" /></span>
								</div>
							</section>

						<!-- First Section -->
							<section id="first" class="main special">
								<header class="major">
									<h2>Traits</h2>
									<p></p>
								</header>
								<ul class="features">
									<li>
										<span class="icon solid major style1 fa-globe"></span>
										<h3>Website</h3>
										<p>Choose one of your favorite websites to discreetly request a wellness check. </p>
									</li>
									<li>
										<span class="icon major style3 fa-address-book"></span>
										<h3>Friends & Family</h3>
										<p>List some friends and or family you would like to notify.</p>
									</li>
									<li>
										<span class="icon major style5 fa-comment"></span>
										<h3>Chat</h3>
										<p>Not sure where to start? Click below to see many free resources to get you started. </p>
									</li>
								</ul>
								<footer class="major">
									<ul class="actions special">
										<li><a href="generic.html" class="button">Learn More</a></li>
									</ul>
								</footer>
							</section>

						<!-- Second Section -->
							<section id="second" class="main special">
								<header class="major">
									<h2>Types of Abuse</h2>
									<p>Abuse is a situation in which a person is treated in a way that is harmful to them.<br /> It can occur to anyone of any age and gender and from any walk of life.<br /> If you or someone you know is being abused, it's important to seek support and help. <br /> Below are just a few of the many types of abuse.</p>
								</header>
								<ul class="statistics">
									<li class="style1">
										<span class="icon fa-hand-rock" style="center"></span>
										<strong>Physical</strong>
									</li>
									<li class="style2">
										<span class="icon fa-heart"></span>
										<strong>Sexual</strong>  
									</li>
									<li class="style3">
										<span class="icon solid fa-theater-masks"></span>
										<strong>Mental / Emotional</strong>
									</li>
									<li class="style4">
										<span class="icon solid fa-theater-masks"></span>
										<strong>Financial</strong>
									</li>
									<li class="style5">
										<span class="icon fa-gem"></span>
										<strong>Cultural / Identity</strong>
									</li>
								</ul>
								<p class="content">Nam elementum nisl et mi a commodo porttitor. Morbi sit amet nisl eu arcu faucibus hendrerit vel a risus. Nam a orci mi, elementum ac arcu sit amet, fermentum pellentesque et purus. Integer maximus varius lorem, sed convallis diam accumsan sed. Etiam porttitor placerat sapien, sed eleifend a enim pulvinar faucibus semper quis ut arcu. Ut non nisl a mollis est efficitur vestibulum. Integer eget purus nec nulla mattis et accumsan ut magna libero. Morbi auctor iaculis porttitor. Sed ut magna ac risus et hendrerit scelerisque. Praesent eleifend lacus in lectus aliquam porta. Cras eu ornare dui curabitur lacinia.</p>
								<footer class="major">
									<ul class="actions special">
										<li><a href="generic.html" class="button">Learn More</a></li>
									</ul>
								</footer>
							</section>

						<!-- Get Started -->
							<section id="cta" class="main special">
							<h2 id="demo">Need Help?</h2>
              <p>If you need emergency assistance, dial 911 immediately. <br />Otherwise click the button below to have police dispatched to your area.</p>
                <button v-on:click="getCurrentPosition()">Click here</button>
								<footer class="major">
									<ul class="actions special">
										<li><a href="/signup" class="button primary">Get Started</a></li>
										<li><a href="generic.html" class="button">Learn More</a></li>
									</ul>
								</footer>
							</section>

					</div>
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
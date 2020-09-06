<template>
  <div class="home">
    
      <!-- Main -->
					<div id="main">

						<!-- Introduction -->
							<section id="intro" class="main">
								<div class="spotlight">
									<div class="content">
										<header class="major">
											<h2>You are not alone.</h2>
										</header>
										<p>On average, 24 people per minute are victims of rape, physical violence or stalking by an intimate partner in the United States — more than 12 million women and men over the course of a year.[i]</p>
										<ul class="actions">
											<li><a href="generic.html" class="button">Learn More</a></li>
										</ul>
									</div>
									<span class="image"><img src="images/pic01.jpg" alt="" /></span>
								</div>
							</section>

						<!-- First Section -->
							<section id="first" class="main special">
								<header class="major">
									<h2>Magna veroeros</h2>
								</header>
								<ul class="features">
									<li>
										<span class="icon solid major style1 fa-code"></span>
										<h3>Ipsum consequat</h3>
										<p>Sed lorem amet ipsum dolor et amet nullam consequat a feugiat consequat tempus veroeros sed consequat.</p>
									</li>
									<li>
										<span class="icon major style3 fa-copy"></span>
										<h3>Amed sed feugiat</h3>
										<p>Sed lorem amet ipsum dolor et amet nullam consequat a feugiat consequat tempus veroeros sed consequat.</p>
									</li>
									<li>
										<span class="icon major style5 fa-gem"></span>
										<h3>Dolor nullam</h3>
										<p>Sed lorem amet ipsum dolor et amet nullam consequat a feugiat consequat tempus veroeros sed consequat.</p>
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
									<h2>Ipsum consequat</h2>
									<p>Donec imperdiet consequat consequat. Suspendisse feugiat congue<br />
									posuere. Nulla massa urna, fermentum eget quam aliquet.</p>
								</header>
								<ul class="statistics">
									<li class="style1">
										<span class="icon solid fa-code-branch"></span>
										<strong>5,120</strong> Etiam
									</li>
									<li class="style2">
										<span class="icon fa-folder-open"></span>
										<strong>8,192</strong> Magna
									</li>
									<li class="style3">
										<span class="icon solid fa-signal"></span>
										<strong>2,048</strong> Tempus
									</li>
									<li class="style4">
										<span class="icon solid fa-laptop"></span>
										<strong>4,096</strong> Aliquam
									</li>
									<li class="style5">
										<span class="icon fa-gem"></span>
										<strong>1,024</strong> Nullam
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
              <p>If you need emergency assistance, dial 911 immediately. Otherwise click the button below to have police dispatched to your area.</p>
                <button v-on:click="getCurrentPosition()">Click here</button>
              <h3 id="showLocation">You are here!</h3>
								</header>
								<footer class="major">
									<ul class="actions special">
										<li><a href="generic.html" class="button primary">Get Started</a></li>
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
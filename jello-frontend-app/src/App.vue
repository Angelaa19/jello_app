<template>
  <div id="app">
    <!-- Wrapper -->
			<div id="wrapper">

				<!-- Header -->
					<header id="header" class="alt">
						<div class="logo"><img src="https://i.pinimg.com/564x/42/9e/89/429e89bf0da5fb2ecdb2c5f5441cb931.jpg" alt="watercolor pizza" style="border-radius: 50%;"></div>
						<h1>Lavender Jello</h1>
						<p style="font-style: italic;">We're all in this together. It's okay to be honest. It's okay to ask for help. It's okay to say you're stuck, or that you're haunted or that you can't begin to let go. We can all relate to those things. Screw the stigma that says otherwise. Break the silence and break the cycle, for you are more than just your pain. You are not alone. And people need other people.<br /> -- Jamie Tworkowski --</p>
					</header>

				<!-- Nav -->
					<nav id="nav">
						<ul>
							<li><a href="/" class="active">Welcome</a></li>
							<li><a href="#first">Features</a></li>
							<li><a href="#second">Second Section</a></li>
							<li><a href="#cta">Get Started</a></li>
						</ul>
					</nav>

				<router-view/>

				<!-- Footer -->
					<footer id="footer">
						<section>
							<h2>Facts sources</h2>
							<p>http://www.annalsofepidemiology.org/article/S1047-2797(12)00024-5/abstract</p>
							<ul class="actions">
								<li><a href="generic.html" class="button">Learn More</a></li>
							</ul>
						</section>
						<section>
							<h2>Etiam feugiat</h2>
							<dl class="alt">
								<dt>Address</dt>
								<dd>1234 Somewhere Road &bull; Nashville, TN 00000 &bull; USA</dd>
								<dt>Phone</dt>
								<dd>(000) 000-0000 x 0000</dd>
								<dt>Email</dt>
								<dd><a href="#">information@untitled.tld</a></dd>
							</dl>
							<ul class="icons">
								<li><a href="#" class="icon brands fa-twitter alt"><span class="label">Twitter</span></a></li>
								<li><a href="#" class="icon brands fa-facebook-f alt"><span class="label">Facebook</span></a></li>
								<li><a href="#" class="icon brands fa-instagram alt"><span class="label">Instagram</span></a></li>
								<li><a href="#" class="icon brands fa-github alt"><span class="label">GitHub</span></a></li>
								<li><a href="#" class="icon brands fa-dribbble alt"><span class="label">Dribbble</span></a></li>
							</ul>
						</section>
						<p class="copyright">&copy; Untitled. Design: <a href="https://html5up.net">HTML5 UP</a>.</p>
					</footer>

			</div>
    
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fef9e7;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>

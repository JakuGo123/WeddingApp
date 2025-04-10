<template>
	<div id="app">
		<nav class="navigation">
			<div class="navigation-buttons">
				<button @click="scrollToSection('our-story')">Our Story</button>
			<button @click="scrollToSection('how-to-get-there')">How to Get There</button>
			<button @click="scrollToSection('gallery')">Gallery</button>
			</div>
			<div class="navigation-title" @click="scrollToTop">
				<h1>Dagmara & Rafał</h1>
			</div>
		</nav>

		<header class="header">

			<div class="header-photos">
				<div class="side-photo left">
					<img src="/images/D_R014.svg" alt="Wedding photo" loading="eager" />
				</div>
				<div class="main-photo">
					<img src="/images/D_R099.svg" alt="Wedding photo" loading="eager" />
					<div class="date">20-09-2025</div>
				</div>
				<div class="side-photo right">
					<img src="/images/D_R119.svg" alt="Wedding photo" loading="eager" />
				</div>
			</div>
		</header>

		<main>
			<section id="our-story" class="section">
				<h2>Our Story</h2>
				<p>Your beautiful love story will be written here...</p>
			</section>

			<section id="how-to-get-there" class="section">
				<h2>How to Get There</h2>
				<p>Venue details and directions will be provided here...</p>
			</section>

			<section id="gallery" class="section">
				<h2>Gallery</h2>
				<p>Your precious moments will be displayed here...</p>
			</section>
		</main>
	</div>
</template>

<script>
export default {
	name: 'App',
	head: {
		title: 'Wesele Dagmary i Rafała',
		meta: [
			{
				name: 'description',
				content: 'Wesele Dagmary i Rafała - 20.09.2025'
			}
		]
	},
	methods: {
		scrollToSection(sectionId) {
			const element = document.getElementById(sectionId);
			element.scrollIntoView({ behavior: 'smooth' });
		},
		scrollToTop() {
			window.scrollTo({
				top: 0,
				behavior: 'smooth'
			});
		}
	}
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Archivo:ital,wght@0,100..900;1,100..900&family=Noto+Serif+Display:ital,wght@0,100..900;1,100..900&display=swap');
#app {
	font-family: "Noto Serif Display", serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #000000;
	max-width: 100vw;
	overflow-x: hidden;
	position: relative;
}

html, body {
	margin: 0;
	padding: 0;
	width: 100%;
	overflow-x: hidden;
}

.header {
	width: 100%;
	height: 100vh;
	margin-bottom: 2rem;
	margin-top: 0;
	position: relative;
	display: flex;
	align-items: center;
	justify-content: center;
}

.header-photos {
	display: flex;
	justify-content: center;
	align-items: center;
	gap: 5rem;
	padding: 1rem;
	height: 100%;
	width: 100%;
}

.side-photo, .main-photo {
	position: relative;
	overflow: hidden;
}

.side-photo img {
	width: 100%;
	height: 100%;
	object-position: center;
	display: block;
}
.main-photo img{
	object-fit: cover;	
	object-position: 40% center;
	height: 100% !important;
	width: 100% !important;
}

.side-photo {
	width: 20%;
	height: 50%;
}
.right img{
	object-position: 70% center;
}

.main-photo {
	width: 30%;
	height: 70%;
}

.date {
	font-family: "Noto Serif Display", serif;
	width: 100%;
	height: auto;
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
	font-size: 10rem;
	font-weight: bold;
	color: Black;
	text-shadow: 2px 2px 4px rgb(255, 255, 255);
	z-index: 10;
}

.navigation {
	font-family: "Noto Serif Display", serif;
	width: 100%;
	padding: 1rem;
	position: fixed;
	top: 0;
	z-index: 100;
	margin-bottom: 0;
	display: flex;
	align-items: center;
	justify-content: space-between;
	z-index: 999;
}

.navigation-buttons {
	display: flex;
	gap: 20px;
}

.navigation-title {
	position: absolute;
	left: 50%;
	transform: translateX(-50%);
	cursor: pointer;
	transition: opacity 0.3s;
}

.navigation-title:hover {
	opacity: 0.8;
}

.navigation-title h1 {
	margin: 0;
	font-size: 4rem;
	font-weight: normal;
}

.navigation button {
	margin: 0.5rem 0;
	padding: 0.5rem 1.5rem;
	font-size: 1.1rem;
	background-color: transparent;
	color: #000000;
	border-radius: 4px;
	border: none;
	cursor: pointer;
	transition: all 0.3s;
	text-align: left;
	width: auto;
}

.navigation button:hover {
	color: #000000;
}

.section {
	padding: 4rem 2rem;
	min-height: 400px;
	height: 100vh;
	background-color: #ffffff;
}

.section:nth-child(odd) {
	background-color: #f8f8f8;
}

h2 {
	margin-bottom: 2rem;
	color: #000000;
}

/* Responsive design */
@media screen and (max-width: 768px) {
	.header-photos {
		flex-direction: column;
		gap: 0.5rem;
		padding: 0.5rem;
	}

	.side-photo {
		width: 100%;
		height: 20%;
	}

	.main-photo {
		width: 100%;
		height: 30%;
	}

	.date {
		font-size: 2rem;
	}

	.navigation {
		padding: 0.5rem;
		width: 100%;
		flex-direction: column-reverse;
		justify-content: center;
	}

	.navigation-title {
		position: relative;
		left: 0;
		transform: none;
		width: 100%;
		text-align: center;
		margin-bottom: 1rem;
	}

	.navigation-buttons {
		width: 100%;
		justify-content: center;
	}

	.navigation button {
		margin: 0 0.5rem;
		padding: 0.3rem 1rem;
		font-size: 1rem;
		text-align: center;
	}
}

@media screen and (max-width: 480px) {
	.date {
		font-size: 4rem;
	}

	.navigation {
		padding: 0.5rem;
		width: 100%;
		flex-direction: column-reverse;
		justify-content: center;
	}

	.navigation-title {
		position: relative;
		left: 0;
		transform: none;
		width: 100%;
		text-align: center;
		margin-bottom: 1rem;
		h1{
			font-size: 2rem;
		}
	}

	.navigation-buttons {
		width: 100%;
		justify-content: center;
	}

	.navigation button {
		margin: 0 0.3rem;
		padding: 0.2rem 0.8rem;
		font-size: 0.9rem;
	}
}
</style>

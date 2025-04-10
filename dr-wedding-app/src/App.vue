<template>
	<div id="app">
		<nav class="navigation">
			<div class="navigation-buttons">
				<button @click="scrollToSection('our-story')">Our Story</button>
			<button @click="scrollToSection('how-to-get-there')">How to Get There</button>
			<button @click="scrollToSection('gallery')">Gallery</button>
			</div>
			<div class="navigation-title">
				<h1>Dagmara & Rafał</h1>
			</div>
		</nav>

		<header class="header">
			<div class="header-photos">
				<div class="side-photo left" style="background-image: url('/images/D&R014.JPG')"></div>
				<div class="main-photo" style="background-image: url('/images/D&R099.JPG')">
					<div class="date">20-09-2025</div>
				</div>
				<div class="side-photo right" style="background-image: url('/images/D&R119.JPG')"></div>
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
		}
	}
}
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #000000;
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

.side-photo {
	width: 20%;
	height: 40%;
	background-color: #f0f0f0;
	background-size: cover;
	background-position: center;
	background-repeat: no-repeat;
}

.main-photo {
	width: 35%;
	height: 60%;
	background-color: #f0f0f0;
	background-size: cover;
	background-position: center;
	position: relative;
}

.date {
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
	font-size: 5rem;
	font-weight: bold;
	color: Black;
	text-shadow: 2px 2px 4px rgb(255, 255, 255);
}

.navigation {
	width: 100%;
	padding: 1rem;
	position: sticky;
	top: 0;
	z-index: 100;
	margin-bottom: 0;
	display: flex;
	align-items: center;
	justify-content: space-between;
}

.navigation-buttons {
	display: flex;
	gap: 20px;
}

.navigation-title {
	position: absolute;
	left: 50%;
	transform: translateX(-50%);
}

.navigation-title h1 {
	margin: 0;
	font-size: 1.5rem;
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
		flex-direction: row;
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
		font-size: 1.5rem;
	}

	.navigation button {
		margin: 0 0.3rem;
		padding: 0.2rem 0.8rem;
		font-size: 0.9rem;
	}
}
</style>

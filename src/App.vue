<template>
	<main class="container">
		<header class="header">
			<img src="./assets/vue.svg" alt="logo" class="header-logo" />
			<h2>My Favorite Movies</h2>
		</header>
		<div class="tabs">
			<button :class="['btn', { btn_green: movieStore.activeTab === 1 }]">Favorite</button>
			<button :class="['btn', { btn_green: movieStore.activeTab === 2 }]">Search</button>
		</div>
		<div class="movies" v-if="movieStore.activeTab === 1">
			<h3 class="heading-3">All Movies</h3>
			<Movie v-for="movie of movieStore.movies" :key="movie.id" :movie="movie" />
		</div>
		<div class="search" v-else>Search</div>
	</main>
</template>

<script setup>
import Movie from './components/MovieList.vue';
import { useMovieStore } from './stores/MovieStore.ts';

const movieStore = useMovieStore();
</script>

<style lang="css">
.container {
	max-width: 1200px;
	margin-left: auto;
	margin-right: auto;
	padding-right: 10px;
	padding-left: 10px;
}
.header {
	display: flex;
	justify-content: center;
	align-items: center;
	padding: 20px;
}
.header-logo {
	max-width: 50px;
	margin-right: 10px;
}
.heading-3 {
	padding-top: 10px;
	padding-bottom: 20px;
	font-size: 20px;
}
.movies {
	display: flex;
	flex-direction: column;
	align-items: center;
}
.btn {
	border: none;
	width: 100px;
	height: 40px;
	font-size: 14px;
	margin: 0 10px;
	border-radius: 10px;
	cursor: pointer;
	background: #efefef;
}
.btn:hover {
	opacity: 0.7;
}
.btn_green {
	background: #37df5c;
}

.tabs {
	display: flex;
	justify-content: center;
	margin-bottom: 30px;
}
</style>

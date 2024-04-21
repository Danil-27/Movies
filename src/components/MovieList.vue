<template>
	<div class="movie">
		<div>
			<img class="movie-img" :src="`${movie.poster_path}`" :alt="movie.original_title" />
		</div>

		<div>
			<div class="movie-name">{{ movie.original_title }} {{ movie.release_date }}</div>
			<span class="movie-overview">{{ movie.overview }}</span>
			<div class="buttons-wrapp">
				<button class="btns movie-buttons-watched">watched</button>
				<button class="btns movie-buttons-delete">delete</button>
			</div>
		</div>
	</div>
</template>

<script setup lang="ts">
import { defineProps } from 'vue';
const props = defineProps({
	movie: {
		type: Object,
		requered: true,
		default: () => {},
	},
});
</script>

<style lang="css" scoped>
.movie {
	display: flex;
	max-width: 700px;
	column-gap: 30px;
	margin-bottom: 20px;
	border: 2px solid #efefef;
	padding: 10px;
	border-radius: 10px;
}

.movie-accept {
	margin-right: 10px;
}

.movie-img {
	width: 200px;
	height: 200px;
	object-fit: cover;
	border-radius: 50%;
}

.movie-name {
	display: flex;
	align-items: center;
	font-size: 20px;
	margin-bottom: 20px;
}
.buttons-wrapp {
	padding-top: 20px;
}
.btns {
	margin-right: 20px;
	color: #fff;
	padding: 15px 30px;
	border-radius: 10px;
	cursor: pointer;
	border: none;
}
.btns:hover {
	opacity: 0.7;
}
.movie-buttons-watched {
	background: #1eb4c3;
}

.movie-buttons-delete {
	background: #ff2a2a;
}
</style>

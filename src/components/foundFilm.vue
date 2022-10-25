<template>
    <div>
        <h1>Пошук</h1>
        <input v-model="findFilm" type="text" name="filmName" id="search" placeholder="А Шо шукаємо?">
        <button @click="searchFilmList">Шукати</button>
        <br>
        <label>
            movie
            <input type="radio" name="type" value="movie" id="" checked>
        </label>
        <label>
            series
            <input type="radio" name="type" value="series" id="">
        </label>
        <label>
            episode
            <input type="radio" name="type" value="episode" id="">
        </label>

        <div v-for="film in films" :key="films.imdbID">
            <img :src="film.Poster" :alt="film.Title">
            <h2>{{ film.Title }}</h2>
        </div>
    </div>
</template>

<script>


const URL = 'http://www.omdbapi.com/?i=tt3896198&apikey=a5a387ab';

export default {
    name: 'foundFilm',
    components: {

    },
    props: {
        msg: String
    },
    data() {
        return {
            films: [],
            findFilm: '',
        }
    },
    async mounted() {
        const res = await fetch(URL);
        const films = await res.json();
        this.films = films.Search;
        
    },
    methods: {
        searchFilmList() {
            // result = URL + `&=${findFilm}`
            // return result

            const newObjectFilm = {
                name: this.findFilm
            }

        }

    }
}
</script>

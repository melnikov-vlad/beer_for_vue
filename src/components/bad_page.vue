<template>
    <div>
        <h1>Великий світ Ріка та Морті</h1>
        <label for="search">
            <h2>Давай число від 1 до 826 і подивимося який персонаж тобі випаде</h2>
            <input class="inp_search" type="text" name="findphrases" id="search" placeholder="Вводи число">
        </label>
        <br>
        <button>Почнемо пошук</button>
        <button>Випадкова персонаж</button>
    </div>
</template>

<script>

const URL = 'https://rickandmortyapi.com/api/character';

export default {
    name: 'bad_page',
    components: {

    },
    props: {
        msg: String
    },
    data() {
        return {
            phrases: [],
            findphrases: '',
        }
    },
    async mounted() {
        const res = await fetch(URL);
        const phrases = await res.json();
        this.phrases = phrases.Search;
        console.log(phrases);
        
    }
}

</script>

<style scoped lang="scss">
.inp_search {
    padding: 20px;
    margin-bottom: 20px;
}
</style>
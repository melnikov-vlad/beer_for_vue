<template>
    <div class="main_wrapper">
        <h1>Великий світ Ріка та Морті</h1>
        <label for="search">
            <h2>Давай число від 1 до 826 і подивимося який персонаж тобі випаде</h2>
            <input v-model="numberPerson" class="inp_search" type="text" name="findphrases" id="search" placeholder="Вводи число">
        </label>
        <br>
        <button @click="searchNumberPerson">Почнемо пошук</button>
        <button>Випадкова персонаж</button>

        <!-- <div v-for="onePers in persones" :key="persones.id">
            <img :src="onePers.image" :alt="onePers.name">
            <h3>{{ onePers.name }}</h3> -->
        <!-- </div> -->
        <div>
            <img :src="persones.image" :alt="persones.name">
            <h3>{{ persones.name }}</h3>
        </div>
    </div>
</template>

<script>

const URL = 'https://rickandmortyapi.com/api/character/';

export default {
    name: 'bad_page',
    components: {

    },
    props: {
        msg: String
    },
    data() {
        return {
            persones: [],
            numberPerson: '',
            
        }
    },
    async mounted() {
        this.searchNumberPerson()
        
    },
    methods: {
        async searchNumberPerson() {
            const res = await fetch(URL + this.numberPerson);
            const persones = await res.json();
            this.persones = persones.Search;  
        },
    }
}

</script>

<style scoped lang="scss">
.inp_search {
    padding: 20px;
    margin-bottom: 20px;
}
</style>
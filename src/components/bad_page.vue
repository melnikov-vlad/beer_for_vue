<template>
    <div class="main_wrapper">
        <h1>Великий світ Ріка та Морті</h1>
        <img class="logo" src="../assets/image/logo-2.webp" alt="">
        <label for="search">
            <h2>Давай число від 1 до 826 і подивимося який персонаж тобі випаде</h2>
            <input v-model="numberPerson" class="inp_search" type="text" name="findphrases" id="search"
                placeholder="Вводи число">
        </label>
        <br>
        <button @click="searchNumberPerson">Почнемо пошук</button>
        <button>Випадкова персонаж</button>
        <!-- if we have single person -->
        <div class="main_img" v-if="persone.name">
            <img :src="persone.image" :alt="persone.name">
            <ul>
                <li><h3>{{ persone.name }}</h3></li>
                <li><h4>{{ persone.gender }}</h4></li>
                <li><h5>{{ persone.status }}</h5></li>
            </ul>
            
        </div>
        <!-- if we have a list of the persones -->
        <div v-if="persones.length && !persone.name" v-for="onePers in persones" :key="persones.id">
            <img :src="onePers.image" :alt="onePers.name">
            <h3>{{ onePers.name }}</h3>
        </div>
        <!-- <div>
            <img :src="persones.image" :alt="persones.name">
            <h3>{{ persones.name }}</h3>
        </div> -->
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
            persone: {},
            numberPerson: '',
            
        }
    },
    props: {
        type: String,
        default: '',
    },
    async mounted() {
        this.searchAllPerson();
    },
    methods: {
        async searchNumberPerson() {
            const res = await fetch(URL + this.numberPerson);
            const persone = await res.json();
            this.persone = persone;
        },
        async searchAllPerson() {
            const res = await fetch(URL);
            const persones = await res.json();
            this.persones = persones.results;  
            
            
        },
    }
}

</script>

<style scoped lang="scss">
.inp_search {
    padding: 20px;
    margin-bottom: 20px;
}

.main_img {
    display: flex;
    justify-content: center;
    align-items: center
}

ul{
    list-style: none;
}


</style>
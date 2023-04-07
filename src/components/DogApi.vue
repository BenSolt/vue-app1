<template>

    <form @submit.prevent="actOnSubmit">
        <button @click="setBreed('mix')">Mix</button>
        <button @click="setBreed('mastiff')">Mastiff</button>
        <button @click="setBreed('labrador')">Labrador</button>
    </form>
    <h2>{{ this.bred }}</h2>

    <div v-if="info">
        <div class="dog-card-container">
            <div v-for="pet in info" :key="pet.id" class="dog-card">
                <h2>{{ this.breed }}</h2>
                <img className="dog-image" alt="random dog" :src="pet" />
            </div>
        </div>
    </div>
</template>

<script>

import axios from 'axios'
import { useState } from '../composables/state';

export default {
    name: 'App',
    created() {
        axios
            .get(`https://dog.ceo/api/breed/${this.breed}/images/random/15`)
            .then((response) => {
                this.info = response.data.message;
                console.log(this.info);
            }, [this.breed])
            .catch(error => {
                console.log(error);
            });
    },

    methods: {
        actOnSubmit() {
                axios
                    .get(`https://dog.ceo/api/breed/${this.breed}/images/random/15`)
                    .then((response) => {
                        this.info = response.data.message;
                        console.log(this.info);
                    }, [this.breed])
                    .catch(error => {
                        console.log(error);
                    });     
            },
    },
    setup() {
        const [breed, setBreed] = useState('mix');

        return {
            breed,
            setBreed,
        };
    },

    data() {
        return {
            info: null,
            // breed: "mix",
        }
    },
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

.weather-forecast {
    list-style: none;
}
</style>

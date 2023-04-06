<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <button @click="add">Add</button>
        <button @click="subtract">Subtract</button>
        <h3>Number: {{ count }}</h3>
        <p>paragraph text goes here...</p>

        <h3 class="todoTitle">To Do List:</h3>

        <div class="todo-list">
            <ul class="todoBox">
                <li v-for="item in todos" v-bind:class="{ active: item.active }" @click="toggleActive(item)" :key="item.id">
                    {{ item.text }}
                </li>
            </ul>
        </div>

        <div>
            {{ info }}
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'MyHelloWorld',
    props: {
        msg: String
    },
    data() {
        return {
            todos: [
                { id: 1, text: 'learn JavaScript' },
                { id: 2, text: 'learn Vue.js' },
                { id: 3, text: 'Build Something Awesome' }
            ],
            count: 0,
            info: null
        };
    },
    methods: {
        add() {
            this.count++
        },

        subtract() {
            this.count--
        },

        toggleActive(item) {
            item.active = !item.active;
        }

    },
    mounted() {
        axios
            .get('https://dog.ceo/api/breed/mix/images/random/15')
            //.then(response => (this.info = response))
            .then((response) => {
                 this.info = response.data.message;
                 console.log(this.info);
             });
    }

//     mounted() {
//         axios
//             .get(`https://dog.ceo/api/breed/${breed}/images/random/15`)
//             .then((response) => {
//                 const doggos = response.data.message;
//                 console.log(doggos);
//             });
//     }, [breed]);
};


</script>
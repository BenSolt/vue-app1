<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <button @click="add">Add</button>
        <button @click="subtract">Subtract</button>
        <h3>Number: {{ count }}</h3>
        <p>paragraph text goes here...</p>
        <h3>Color: {{ color }}</h3>
        <h3 class="todoTitle">To Do List:</h3>
        <div class="todo-list">
            <ul class="todoBox">
                <li class="initial" :class="{ color }"  @click="changeColor" v-for="x in todos" :key="x.id">
                    {{ x.text }}
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'MyHelloWorld',
    props: {
        msg: String
    },
    data() {
        return {
            todos: [
                { text: 'learn JavaScript' },
                { text: 'learn Vue.js' },
                { text: 'Build Something Awesome' }
            ],
            count: 0,
            color: false
        };
    },
    methods: {
        add() {
            this.count++
        },

        subtract() {
            this.count--
        },
        changeColor() {
            this.color = !this.color
        }

    },
};

</script>
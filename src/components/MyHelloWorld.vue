<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <h6>{{ count }}</h6>
        <p>
            paragraph
        </p>

        <ul>
            <li>
                a
            </li>
        </ul>

        <ul>
            <li v-for="x in todos" :key="x.id">
                {{ x.text }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'MyHelloWorld',
    props: {
        msg: String,
        count: Number
    },
    todos: [
        {text: 'learn JavaScript'},
        {text: 'learn Vue.js'},
        { text: 'Build Something Awesome' }
    ]
}
</script>
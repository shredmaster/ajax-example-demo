<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <ul>
            <li><input name="search" v-model="search"></li>
            <li>
                <button @click="feelLucky">Feel Lucky</button>
            </li>
        </ul>
        <h3>{{ response.description }}</h3>
    </div>
</template>

<script>

    import axios from 'axios'

    export default {
        name: 'HelloWorld',
        data() {
            return {
                search: '',
                response: {}
            }
        },
        props: {
            msg: String
        },
        methods: {
            async feelLucky() {
                try {
                    const response = await axios.post('/search', {search: this.search})
                    this.response = response
                } catch (e) {
                    this.response = {
                        description: `Your search - ${this.search} - did not match any documents.`
                    }
                }
            }
        },
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }

    input {
        height: 30px;
        width: 300px;
        line-height: 14px;
    }

    button {
        width: 80px;
        height: 30px;
    }
</style>

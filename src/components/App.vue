<template>
    <div id="app">
        <h3>Check dem jokes bro</h3>
        <div style="margin-bottom: 30px;">
            <button class="btn btn-danger" @click="initJokes">Add ten random jokes</button>
            <button class="btn btn-success" @click="addJoke">Add one random jokes</button>
        </div>
        <div class="text-center">
            <span v-for="type in types" v-bind:value="type" checked>
                <input type="checkbox" v-bind:value="type" v-model="checkedTypes">
                <label>{{ type }}</label>
            </span>
        </div>
        <Joke v-for="(joke, index) in jokes" v-bind:joke="joke" v-bind:key="joke" v-bind:index="index" v-show="checkedTypes.includes(joke.type)"></Joke>
    </div>
</template>

<script>
import { mapActions } from 'vuex'
import Joke from './Joke'

export default {
    data: function() {
        return {
            types: ['general','knock-knock','programming'],
            checkedTypes: ['general','knock-knock','programmin']
        }
    },
    methods: mapActions([
        'initJokes','addJoke'
    ]),
    components: {
        Joke: Joke
    },
    computed: {
        jokes: function() {
            return this.$store.state.jokes;
        } 
    }
}
</script>
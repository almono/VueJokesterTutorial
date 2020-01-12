<template>
    <div class="col-md-3" style="height: 150px; margin-bottom: 5px; padding: 10px;">
        <div class="joke-body">
            <div class="col-md-12 joke-title">
                <h5 class="col-md-6 text-left">{{ joke.id }}</h5>
                <h5 class="col-md-6 text-right" style="cursor: pointer;" @click="removeJoke(index)">X</h5>
            </div>
            <div class="col-md-12 joke-joke">
                <span class="col-md-12 joke-setup">{{ joke.setup }}</span>
                <span class="col-md-12 joke-punchline">{{ joke.punchline }}</span>
            </div>
        </div>
    </div>
</template>

<script>
import { mapActions } from 'vuex'

export default {
    name: 'Joke',
    props: ['joke', ],
    methods: mapActions([
        'removeJoke'
    ])
}
</script>

<style scoped>
    .joke-body {
        border: 1px solid #ddd;
        height: 100%;
    }
    .joke-title {
        border-bottom: 1px solid #eee;
        font-weight: 600;
        text-align: center;
        font-size: 14px;
    }
    .joke-joke {
        height: 100px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>
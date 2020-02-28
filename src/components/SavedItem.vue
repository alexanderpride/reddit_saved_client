<template>
    <div>
        <p v-if="error">
            {{error}}
        </p>
        <h3 v-for="item in items" v-bind:key="item">
            {{item}}
        </h3>
    </div>
</template>

<script>
    import axios from 'axios';

    export default {
        name: "SavedItem",
        data: function () {
            return {
                items: [],
                error: null
            }
        },
        methods: {
            getItems: function () {
                axios.get('http://localhost:3000/content/').then(function (response) {
                    this.items = response.data;
                }).catch(function (error) {
                    this.error = error
                })
            }
        },
        mounted: function () {
            this.getItems();
        }
    }
</script>

<style scoped>
    div {
        width: 100%;
        background-color: green;
    }
</style>
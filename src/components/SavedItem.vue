<template>
    <div>
        <p v-if="error">
            {{error}}
        </p>
        <div v-for="item in items" v-bind:key="item.id" class="items">
            <div v-if="item.type === 'Comment'">
                <Comment v-bind:item="item"></Comment>
            </div>

            <h3 v-else>
                {{item}}
            </h3>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    import Comment from "@/components/Comment";

    export default {
        name: "SavedItem",
        data: function () {
            return {
                items: [],
                error: null
            }
        },
        components: {
          Comment
        },
        methods: {
            getItems: function () {
                axios.get('http://localhost:3000/content/', {
                    withCredentials: true
                }).then((response) => {
                    this.items = response.data;
                }).catch((error) => {
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
        /*width: 100%;*/
    }

    h3{
        margin-bottom: 5px;
        background-color: green;
    }

    .items{
        margin-bottom: 8px;
    }
</style>
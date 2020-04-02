<template>
    <div>
    <div class="container">
        <div class="sfrBar">
            <p>Category</p>
        </div>

        <div class="body">
            <p>{{item.body}}</p>
        </div>

        <div class="redditBar">

        </div>

    </div>

    <div>
        {{item}}
    </div>
    </div>
</template>

<script>
    export default {
        name: "Comment",
        props: ['item']
    }
</script>

<style scoped>
    p{
        color: #5a5d60;
        margin: 0;
    }

    .container{
        background-color: #CCCECA;
        border: 2px solid #5a5d60;
        border-radius: 10px;
    }

    .sfrBar{
        background-color: white;
        border-radius: 8px 8px 0 0;
        padding: 2px;
    }
</style>
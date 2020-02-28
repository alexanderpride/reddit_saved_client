<template>
    <div>
        <form>
            <input type="text" v-model="searchTerm" placeholder="Search...">
            <label>Sort By</label>

            <div class="sortByButtons">
                <input type="radio" v-model="sortByTerm" value="mr" id="mr">
                <label for="mr">Most Recent</label>

                <input type="radio" v-model="sortByTerm" value="lr" id="lr">
                <label for="lr">Least Recent</label>
            </div>


            <label>Filter</label>
            <div class="savedTypeButtons">
                <input type="checkbox" v-model="checkCommentTerm" id="cc">
                <label for="cc">Comments</label>

                <input type="checkbox" v-model="checkPostTerm" id="cp">
                <label for="cp">Posts</label>
            </div>



        </form>
    </div>
</template>

<script>
    export default {
        name: "Panel",
        data: function () {
            return {
                searchTerm: '',
                sortByTerm: '',
                checkCommentTerm: true,
                checkPostTerm: true
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: #5a5d60;
    }

    input[type=text] {
        font-family: inherit;
        border-radius: 5px;
        width: 95%;
        margin: 2%;
        padding: 5px 0 5px 2px;
    }

    form {
        font-family: 'Roboto Slab', serif, Avenir, Helvetica, Arial, sans-serif;
        color: white;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .sortByButtons, .savedTypeButtons{
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-around;
        width: 100%;
    }
</style>
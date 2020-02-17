<template>
    <div>
        <h2>Saved for Reddit</h2>

        <button>Logout</button>
    </div>
</template>

<script>
    export default {
        name: "Header"
    }
</script>

<style scoped>
    div {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
        background-color: #BC2C1A;
    }

    h2 {
        font-family: 'Roboto Slab', Avenir, Helvetica, Arial, sans-serif;
        color: white;
        margin-left: 4%;
    }

    button{
        margin-right: 4%;
        font-family: 'Roboto Slab', serif, Avenir, Helvetica, Arial, sans-serif;
        font-weight: bold;
        color: white;
        background-color: #BC2C1A;
        padding: 10px 20px;
        border-radius: 10px;
        border: white 2px solid;
        transition: background 250ms ease-in-out;
    }

    button:hover{
        color: #BC2C1A;
        background-color: white;
    }
</style>
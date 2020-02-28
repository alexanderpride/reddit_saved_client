<template>
    <section>
        <div>

            <h1>Welcome to Saved for Reddit</h1>

            <p>Saved for Reddit needs your permission to access your profile</p>

            <button @click="link">Link profile<img src="../assets/reddit.png" alt="Reddit Logo"> </button>

        </div>
    </section>
</template>


<script>
    import axios from 'axios'

    export default {
        name: "Homepage",
        data: function () {
            return {

            }
        },
        methods: {
            link: function () {
                axios.get('http://localhost:3000/users/auth_link', {
                    withCredentials: true
                })
                    .then(function (response) {
                        console.log(document.cookie);
                        console.log(response);
                        return response
                    }).then(function (response) {
                        window.location.href = response.data['auth_link'];
                    }).catch(function (error) {
                        console.log(error)
                    });
            }
        }
    }
</script>

<style scoped>

    section{
        height: 90vh;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    section div{
        height: 50%;
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
        align-items: center;
        padding: 0;
        margin: auto auto;
        text-align: center;
    }

    button{
        font-family: 'Roboto Slab', serif, Avenir, Helvetica, Arial, sans-serif;
        font-weight: bold;
        font-size: 1.5em;
        color: white;
        background-color: #BC2C1A;
        padding: 20px 40px;
        border-radius: 10px;
        border: #BC2C1A 2px solid;
        transition: background 250ms ease-in-out;
        display: flex;
        flex-direction: row;
        align-items: center;
        white-space: nowrap;
    }

    button img {
        width: 64px;
        height: 64px;
        margin-left: 5%;
    }

    button:hover{
        color: #BC2C1A;
        background-color: white;
        border: #BC2C1A 2px solid;
    }



</style>
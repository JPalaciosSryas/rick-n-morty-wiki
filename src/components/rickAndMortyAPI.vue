<template>
    <div>
        <div class="header-container">
            <h1>The Rick & Morty API</h1>
        </div>
        <div class="main-container" >
            <div v-for="character in characters.results" :key="character.id">
                <div class="character-container">
                    <h1>{{ character.name }}</h1>
                    <img :src="character.image" />
                    <p>Status: <span id="status" :class="character.status == 'Alive' ? 'green' : character.status == 'Dead' ? 'red' : 'gray'">&#9679;</span> {{ character.status }}</p>
                    <p>Type: {{ character.type ? character.type : "N/D" }}</p>
                    <p>Gender: {{ character.gender}}</p>
                    <p>Location: {{ character.location.name}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'rickAndMortyAPI',
        data() {
            return {
                characters: []
            }
        },
        methods: {
            callingAPI() {
                fetch("https://rickandmortyapi.com/api/character").then(res => res.json().then(json => {
                    this.characters = json;
                }))
            }
        },
        mounted() {
            this.callingAPI();
        }
    }
</script>

<style>
    .header-container {
        margin: 0 auto 60px;
        height: 180px;
        background-color: #333;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .header-container h1 {
        margin: 0;
        font-family: 'Courier New', Courier, monospace;
        font-size: 42px;
        color: white;
    }

    .main-container {
        width: 1170px;
        margin: 0 auto;
        display: flex;
        flex-wrap: wrap;
        background-color: gray;
        justify-content: space-between;
        align-items: center;
    }
    
    .character-container {
        font-family: 'Courier New', Courier, monospace;
        font-size: 16px;
        font-weight: bold;
        height: 360px;
        width: 180px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        margin: 12px;
        background-color: green;
        border: 5px solid gold;
        border-radius: 16px;
        padding: 16px;
    }

    .character-container h1 {
        color: gold;
        margin: 0 auto;
        font-size: 24px;
    }

    .character-container img {
        margin: 8px auto;
        width: 180px;
        height: auto;
    }

    .character-container p {
        color: silver;
        width: 100%;
        margin: 0 auto;
        text-align: left;
    }

    .green {
        color: lightgreen;
    }

    .red {
        color: red;
    }

    .gray {
        color: #333;
    }

</style>
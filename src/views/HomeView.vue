<template>
<div class="home">
    <h1>Star Wars Api</h1>
    <img src="../assets/Star-wars-logo-new-tall.webp" alt="" width="600" height="200">
    <div class="container">
      <!-- characters -->
    <div class="people-wrapper">
        <h2>Star Wars Character facts</h2>
        <button class="people-btn" v-on:click="getPeople">Go</button>
        <div class="content">
            <div class="label">NAME:
                <div class="item">{{ people.name }}</div>
            </div>
            <div class="label">GENDER:
                <div class="item">{{ people.gender }}</div>
            </div>
            <div class="label">HEIGHT:
                <div class="item">{{ people.height }}</div>
            </div>
            <div class="label">HAIR COLOUR:
                <div class="item">{{ people.hair_color }}</div>
            </div>
            <div class="label">SKIN COLOUR:
                <div class="item">{{ people.skin_color }}</div>
            </div>
        </div>
    </div>
    <!-- planets -->
    <div class="planet-wrapper">
        <h2>Star Wars Planet facts</h2>
        <button class="people-btn" v-on:click="getPlanets">Go</button>
        <div class="content">
            <div class="label">NAME:
                <div class="item">{{ planets.name }}</div>
            </div>
            <div class="label">POULATION:
                <div class="item">{{ planets.population }}</div>
            </div>
            <div class="label">CLIMATE:
                <div class="item">{{ planets.climate }}</div>
            </div>
        </div>
    </div>
    </div>
  
</div>
</template>

<script>
export default {
    name: 'HomeView',
    components: {},
    data() {
        return {
            people: [],
            planets: [],
            id: ''
        }

    },
    methods: {
        getPeople() {
            let id = Math.floor(Math.random() * 100);
            fetch(`https://swapi.dev/api/people/${this.id, id}/`)
                .then((response) => {
                    console.log(id)
                    return response.json()
                }).then((data) => {
                    this.people = data;

                    console.log(this.people)
                })
        },
        getPlanets() {
            let id = Math.floor(Math.random() * 50);
            fetch(`https://swapi.dev/api/planets/${this.id, id}/`)
                .then((response) => {
                    console.log(id)
                    return response.json()
                }).then((data) => {
                    this.planets = data;

                    console.log(this.planets)
                })
        }
    },
    mounted() {

    }
}
</script>

<style scoped>
.home {
    width: 100%;
    max-width: 50%;
    margin: auto;
}
.container {
  display: flex;
}
.img {
    margin: auto;
}

.people-wrapper, .planet-wrapper {
    background-color: #000;
    padding: 15px;
    border: 4px dotted #f1f446;
    margin: 0px 10px 0px 10px;
}

h2,
.label {
    color: #fff;

    font-weight: bold;
}

.item {
    font-weight: bold;
    margin: 10px 0px 10px 0px;
    color: #f1f446;
}

.people-btn {
    color: #000;
    background-color: #f1f446;
    outline: none;
    border: none;
    border-radius: 10px;
    padding: 5px 10px;
    margin-bottom: 10px;
    cursor: pointer;
}
</style>

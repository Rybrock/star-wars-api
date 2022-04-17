<template>
<div class="home">
    <img src="../assets/Star-wars-logo-new-tall.webp" alt="">
    <h1>Star Wars Factiods</h1>
    <div class="container">
        <!-- characters -->
        <div class="people-wrapper">
            <h2>Star Wars Character facts</h2>
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
            <button class="people-btn" v-on:click="getPeople">Go</button>
            </div>
        </div>
        <!-- planets -->
        <div class="planet-wrapper">
            <h2>Star Wars Planet facts</h2>
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
                <div class="label">ORBITAL PERIOD:
                    <div class="item">{{ planets.orbital_period }}</div>
                </div>
                <div class="label">DIAMETER:
                    <div class="item">{{ planets.diameter }}</div>
                </div>
            <button class="people-btn" v-on:click="getPlanets">Go</button>
            </div>
        </div>
        <!-- starships -->
        <div class="planet-wrapper">
            <h2>Star Wars Starships facts</h2>
            <div class="content">
                <div class="label">NAME:
                    <div class="item">{{ ships.name }}</div>
                </div>
                 <div class="label">MODEL:
                    <div class="item">{{ ships.model }}</div>
                </div> 
                <div class="label">STARSHIP CLASS:
                    <div class="item">{{ ships.starship_class }}</div>
                </div> 
                <div class="label">MANUFACTURER:
                    <div class="item">{{ ships.manufacturer }}</div>
                </div>
                <div class="label">CONSUMABLES:
                    <div class="item">{{ ships.consumables }}</div>
                </div>
            <button class="people-btn" v-on:click="getShips">Go</button>
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
            ships: [],
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
        },
        getShips() {
            let id = Math.floor(Math.random() * 10);
            fetch(`https://swapi.dev/api/starships/${this.id, id}/`)
                .then((response) => {
                    console.log(id)
                    return response.json()
                }).then((data) => {
                    this.ships = data;

                    console.log(this.ships)
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
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.container {
    display: flex;
    justify-content: center;
    align-items: center;
}

img {
    margin: auto;
    width: 100%;
    margin-bottom: 20px;
}

.people-wrapper,
.planet-wrapper {
    background-color: #000;
    padding: 15px;
    border: 4px dotted #f1f446;
    margin: 5px 10px 5px 10px;
    width: 100%;
    min-width: 33%;
    height: 100%;
    min-height: 500px;
    border-radius: 20px;
    
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

@media only screen and (max-width: 780px) {
    .container {
        flex-direction: column;
        justify-content: center;
    }
}
</style>

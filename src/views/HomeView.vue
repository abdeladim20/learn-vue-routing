<script setup>
import cars from "../data/cars.json"
import {RouterLink} from "vue-router"
</script>

<template>
    <div>
        <h1>Home View</h1>
        <div class="cars">
            <RouterLink :to="`/cars/${car.id}`" v-for="car in cars" :key="car.id" href="">
                {{ car.name }}
            </RouterLink>
        </div>
    </div>
</template>

<style scoped>
.cars {
    display: flex;

}

.cars a {
    text-decoration: none;
    color: black;
    width: 100%;
    box-shadow: 1px, 1px 1px rgb(0, 0, 0, 0.166)
}
</style>
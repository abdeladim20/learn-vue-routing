<script setup>
import { useRoute, useRouter, RouterView } from "vue-router"
import cars from "../data/cars.json"

const route = useRoute()
const router = useRouter()
const carId = parseInt(route.params.id)

const showContact = () => {
    if (carId === 4) {
        return;
    } else {
        return router.push(`/cars/${carId}/contact`)
    }
}

const car = cars.find(c => c.id === parseInt(route.params.id))


</script>

<template>
    <div v-if="car">
        <h1>Car View</h1>
        <p>{{ car.name }}</p>
        <p>{{ car.year }}</p>
        <p>{{ car.price }}</p>
        <button @click="showContact()">Click Me For Contact</button>
        <RouterView />
    </div>
    <div v-else>
        <h1>Car Not Found</h1>
    </div>
</template>
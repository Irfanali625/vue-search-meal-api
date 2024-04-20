<template>
     <div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
           <MealItems v-for="meal of meals" :key="meal.idMeal" :meal="meal" />
        </div>
</template>

<script setup>
import { computed, onMounted, ref } from "vue";
import MealItems from "../components/MealItems.vue";
import axiosClient from "../axiosClient.js"


const meals = ref([]);

onMounted(async () => {
    const response = await axiosClient.get('search.php?f=r')
    console.log(response.data)
    meals.value = response.data.meals;
})
</script>

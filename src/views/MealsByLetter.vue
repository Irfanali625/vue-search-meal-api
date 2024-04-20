<template>
    <div class="flex justify-center gap-2 mt-2">
        <router-link :to="{ name: 'byLetter', params: { letter } }" v-for="letter of letters" :key="letter">
            {{ letter }}
        </router-link>
    </div>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
       <MealItems v-for="meal of meals" :key="meal.idMeal" :meal="meal" />
    </div>
</template>

<script setup>
import { computed, onMounted, watch } from "vue";
import { useRoute } from "vue-router";
import MealItems from "../components/MealItems.vue";
import store from "../store";

const route = useRoute();
watch(route, () => {
    store.dispatch('searchMealsByLetter', route.params.letter)
})

const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("");
const meals = computed(() => store.state.mealsByLetter)

onMounted(() => {
    store.dispatch('searchMealsByLetter', route.params.letter)
})
</script>
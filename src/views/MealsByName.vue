<template>
     <div class="p-8 pb-0">
        <input type="text" v-model="keyword" class="rounded w-full" placeholder="Search for meals" @change="searchMeals">
     </div> 
     <div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
       <MealItems v-for="meal of meals" :key="meal.idMeal" :meal="meal" />
     </div>
</template>

<script setup>
import { computed, onMounted, ref, watch } from "vue";
import { useRoute } from 'vue-router';
import MealItems from "../components/MealItems.vue";
import store from "../store";

const meals = computed(() => store.state.searchMeals);

const route = useRoute();

const keyword = ref('');
function searchMeals() {
    store.dispatch('searchMeals', keyword.value)
}

onMounted(() => {
    keyword.value = route.params.name;
    if (keyword.value) {
        searchMeals();
    }
})
</script>
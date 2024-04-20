<template>
     <div class="bg-white shadow rounded-xl">
                <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }">
                    <img :src="meal.strMealThumb" :alt="meal.strMeal" class="rounded-t-xl w-full h-48 object-cover">
                </router-link>
                <div class="p-3">
                   <h1 class="font-bold">{{ meal.strMeal }}</h1>
                 <p class="text-justify mb-4">Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste aut facilis impedit veritatis. In, libero officia laudantium ea sint, facere eius quidem, libero officia laudantium ea sint, facere eius quidem</p>
                
                 <div>
                     <YouTubeButton :href="meal.strYoutube">YouTube</YouTubeButton>
                 </div>
                
               </div>
            </div>
</template>

<script setup>
import YouTubeButton from "../components/YouTubeButton.vue";

const { meal } = defineProps({
    meal: {
        required: true,
        type: Object
    }
})

</script>
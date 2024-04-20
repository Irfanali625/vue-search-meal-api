<template>
    <Header class="bg-white shadow-md h-14 flex justify-between items-stretch text-red-500">
        <router-link :to="{ name: 'home' }" class="px-2 inline-flex items-center">
          Home
        </router-link>
        <div class="flex items-center gap-1">
          <router-link :to="{ name: 'byName' }" class="px-2 h-full inline-flex items-center transition-all hover:bg-purple-100">
            Search Meals
          </router-link>
          <router-link :to="{ name: 'byLetter' }" class="px-2 h-full inline-flex items-center transition-all hover:bg-purple-100">
            Meals by Letter
          </router-link>
        </div>
      </Header>
</template>
<template>
    <div class="h-full bg-gray-100">
    <Navbar />
      <Main>
        <router-view />
      </Main>
    </div>
</template>

<script setup>
import Navbar from '../components/Navbar.vue'
</script>
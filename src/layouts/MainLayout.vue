<script setup lang="ts">
import Navbar from '../components/Navbar.vue';
import HomePage from '../Pages/HomePage.vue';
</script>

<template>
    <div>
        <div><Navbar/></div>
        <div>
            <router-view/>  
        </div>
    </div>
</template>
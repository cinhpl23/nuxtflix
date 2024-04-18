<template>
    <footer class="bg-black text-white mg-9">
        <p>vueflix &copy; {{ currentYear }}</p> 
    </footer>
</template>
    
<script setup>
    let currentYear = new Date().getFullYear();
</script>
<script setup>
import { ref } from 'vue'
import page1 from './components/page1.vue'
</script>

<template>
    <header class="d-flex flex-wrap justify-content-center py-3 mb-4 b " style="width: 100%;  background-color: rgb(22, 22, 22);">
        <a href="/" class="d-flex align-items-center mb-3 mb-md-0 me-md-auto link-body-emphasis text-decoration-none">
        <svg class="bi me-2" width="50" height="70"><use xlink:href="#bootstrap"></use></svg>
        <span class="fs-3" style="color: white;"><h2>จองโต๊ะร้านอาหาร</h2></span>
        </a>
    </header>
  
    <page-1/>
    
    <footer>@Thonthus Prangpetch 6504101343</footer>

</template>

<style scoped>
body{
  background-color: rgb(29, 29, 29);
  margin: 0%;
  padding: 0%;
}

footer{
    margin-top: 20px;
    bottom: 0%;
    text-align: center;
    width: 100%;
    background-color: rgb(219, 219, 219);
}
</style>

<template>
    <div id="app" class="bg-gray-50 container mx-auto p-12 w-full lg:w-1/2 lg:px-24 shadow">
        <header-title/>
        <calculations/>
    </div>
</template>

<script>
import HeaderTitle from './components/HeaderTitle.vue'
import Calculations from './components/Calculations.vue'

export default {
    components: {
        HeaderTitle,
        Calculations
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
    margin-bottom: 120px;
}
</style>

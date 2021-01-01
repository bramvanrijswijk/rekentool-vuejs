<template>
    <div>
        <calculation v-for="i in 30" :key="i" />
    </div>
</template>

<script>
    import Calculation from './Calculation.vue'

    export default {
        name: "Calculations",
        components: {
            'calculation': Calculation
        }
    }
</script>

<style scoped>

</style>
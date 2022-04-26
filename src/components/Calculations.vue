<template>
    <div>
        <calculation v-for="i in 100" :key="i"/>
    </div>
</template>

<script>
import Calculation from './Calculation.vue'

export default {
    components: {
        Calculation
    }
}
</script>

<style scoped>

</style>
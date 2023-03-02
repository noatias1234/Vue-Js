<template>
    <div>
        <h2>Child c component</h2>
        <h3>Child compoennt C user name - {{ userName }}</h3>
        <h3>Child compoennt C composition user name - {{ childUserName }}</h3>

        <h3>Child compoennt C count - {{ childCount }}</h3>
        <h3>Child compoennt C hero - {{ firstName }} {{ lastName }}</h3>

        <button @click="incrementCount">Increase count</button>

    </div>
</template>

<script>
import { inject, toRefs } from 'vue';
export default {
    name: `Childc`,
    setup() {
        const childUserName = inject('c_userName', 'Default username')
        const childCount = inject('c_count', 0)
        const childHero = inject('c_hero', {})
        const incrementCount = inject('incrementCount')




        return {
            childUserName,
            childCount,
            ...toRefs(childHero),
            incrementCount
        }
    },
    inject: ['userName'],
}
</script>

<style scoped></style>
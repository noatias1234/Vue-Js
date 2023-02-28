<template>
    <div>
        <h2>{{ firstName }}{{ lastName }}</h2>
        <button @click="changeHero">Change Name</button>

        <h2>{{ count }}</h2>
        <button @click="increasementCount">Increase</button>
    </div>
</template>

<script>
import { ref, reactive, toRefs } from 'vue';
export default {
    name: `Methods`,
    setup() {
        const count = ref(0)
        const state = reactive({
            firstName: 'Bar',
            lastName: 'Atias'
        })

        function increasementCount() {
            count.value++;
        }

        function changeHero() {
            state.firstName = 'Bat',
                state.lastName = 'Man'
        }

        return {
            count,
            increasementCount,
            changeHero,
            ...toRefs(state),
        }
    }
}

</script>

<style scoped></style>
<template>
    <div>
        <input type="text" placeholder="First Name" v-model="refFirstName">
        <input type="text" placeholder="Last Name" v-model="refLastName">
        <h2>REF full name - {{ refFullName }}</h2>


        <input type="text" placeholder="First Name" v-model="reactiveFirstName">
        <input type="text" placeholder="Last Name" v-model="reactiveLastName">
        <h2>Reactive full name - {{ reactiveFullName }}</h2>


    </div>
</template>

<script>
import { ref, reactive, computed, toRefs } from 'vue';
export default {
    name: `computed`,
    setup() {
        const refFirstName = ref('')
        const refLastName = ref('')

        const refFullName = computed(function () {
            return `${refFirstName.value} ${refLastName.value}`
        });

        const state = reactive({
            reactiveFirstName: '',
            reactiveLastName: ''
        })

        const reactiveFullName = computed(function () {
            return `${state.reactiveFirstName} ${state.reactiveLastName}`
        })

        return {
            refFirstName,
            refLastName,
            ...toRefs(state),
            refFullName,
            reactiveFullName
        }
    }
}
</script>

<style scoped></style>
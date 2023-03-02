<template>
    <div>
        <input type="text" placeholder="First name" v-model="firstName">
        <input type="text" placeholder="Last name" v-model="lastName">

    </div>
</template>

<script>
import { ref, watch } from 'vue';
export default {
    name: `Watch`,
    setup() {
        const firstName = ref('')
        const lastName = ref('Wayne')


        watch(
            [firstName, lastName],
            (newValues, oldValues) => {
                console.log('first name old value', oldValues[0]);
                console.log('first name new value', newValues[0]);
                console.log('last name old value', oldValues[1]);
                console.log('last name old value', newValues[1]);
            },
            {
                immediate: true
            }
        )

        return {
            firstName,
            lastName
        }
    }
}
</script>

<style scoped></style>
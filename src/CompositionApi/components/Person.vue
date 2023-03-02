<template>
    <div>
        <input type="text" placeholder="First name" c-model="firstName" />
        <input type="text" placeholder="Last name" c-model="lastName" />

    </div>
    <PersonGreeting :firstName="firstName" :lastName="lasttName" />
</template>

<script>
import { ref } from 'vue';
import PersonGreeting from './PersonGreeting.vue';
export default {
    name: `person`,
    components: { PersonGreeting },
    setup() {
        const firstName = ref('')
        const lasttName = ref('')

        return {
            firstName,
            lasttName
        }

    }

}
</script>

<style scoped></style>
<template>
    <div>
        Hello {{ fullName }}
        <button @click="sendEvent">SEND</button>
    </div>
</template>

<script>
import { computed } from 'vue';
export default {
    name: `PersonGreeting`,
    setup(props, context) {
        console.log(context);
        const fullName = computed(() => {
            return `${props.firstName} ${props.lastName}`
        })

        function sendEvent() {
            context.emit('callHeroes', props.firstName)
        }
        return {
            fullName,
            sendEvent
        }
    }
    ,

    props: ['firstName', 'lastName'],
    // computed: {
    //     fullName() {
    //         return `${this.firstName} ${this.lastName}`
    //     }
    // }
}
</script>

<style scoped></style>
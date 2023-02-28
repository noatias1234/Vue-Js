<template>
    <div>
        {{ state.firstName }} {{ state.lastName }}
    </div>
</template>

<script>
import { reactive, toRefs } from 'vue';
export default {
    name: `Demo 2`,
    setup() {
        const state = reactive({
            firstName: 'Bruc',
            lastName: 'Wayne'
        })

        setTimeout(() => {
            state.firstName = 'Bar',
                state.lastName = 'Atias',
                console.log(state);
        }, 2000);

        return toRefs(state);
    },


}


</script>

<style scoped></style>
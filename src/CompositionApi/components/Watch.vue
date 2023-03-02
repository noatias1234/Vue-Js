<template>
    <div>
        <input type="text" placeholder="First name" v-model="firstName">
        <input type="text" placeholder="Last name" v-model="lastName">

        <input type="text" placeholder="Reactive - First name" v-model="fName">
        <input type="text" placeholder="Reactive - Last name" v-model="lName">
        <input type="text" placeholder="Hero Name" v-model="options.heroName">

    </div>
</template>

<script>
import { ref, watch, reactive, toRefs } from 'vue'
import _ from 'lodash'

export default {
    name: `Watch`,
    setup() {
        const firstName = ref('')
        const lastName = ref('Wayne')

        const state = reactive({
            fName: '',
            lName: '',
            options: {
                heroName: ''
            }
        })

        //2 deep options to watch nested properties
        watch(() => state.options,
            function (newValue, oldValue) {
                console.log('Old value:', oldValue);
                console.log('New value:', newValue);

            },
            {
                deep: true,
            })

        // yarn add loadash
        watch(() => _.cloneDeep(state.options),
            function (newValue, oldValue) {
                console.log('Old value:', oldValue);
                console.log('New value:', newValue);

            })

        watch(() => {
            return { ...state }
        },
            function (newValue, oldValue) {
                console.log('fName old value:', oldValue.fName);
                console.log('fName new value:', newValue.fName);
                console.log('lName old value:', oldValue.lName);
                console.log('lName new value:', newValue.lName);

            })
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
            lastName,
            ...toRefs(state)
        }
    }
}
</script>

<style scoped></style>
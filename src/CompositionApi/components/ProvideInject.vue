<template>
    <div>
        <h2>Parent component {{ name }}</h2>
        <h2>Parent component- count {{ count }}</h2>
        <h2>Parent component hero {{ firstName }} {{ lastName }}</h2>

        <ChildA />
    </div>
</template>

<script>
import { provide, toRefs, reactive, ref } from 'vue';
import ChildA from './ChildA.vue';
export default {
    components: { ChildA },
    name: 'Provide-inject',
    setup() {
        provide('c_userName', 'Codevolution')

        const count = ref(0)
        const state = reactive({
            firstName: 'Bruc',
            lastName: 'Wayne'
        })

        function incrementCount() {
            count.value++;
        }

        provide('c_count', count)
        provide('c_hero', state)
        provide('incrementCount', incrementCount)


        return {
            count,
            ...toRefs(state),
            incrementCount
        }
    },
    data() {
        return {
            name: 'Vishwas'
        }
    },

    provide() {
        return {
            userName: this.name
        }
    },
}
</script>

<style scoped></style>
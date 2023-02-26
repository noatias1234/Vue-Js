<template>
    <div>
        <h2>Options - {{ o_firstName }}</h2>
        <h2>Options - {{ o_firstName }}{{ o_lastName }} a.k.a {{ o_heroName }}</h2>

        <h2>Composition - {{ c_firstName }}{{ c_lastName }}{{ c_heroName }}</h2>
        <h2>Composition - {{ greet }}</h2>
        <h2>Composition - {{ greetHero }}</h2>

        <h2>Composition - {{ reactiveGreetHero }}</h2>
    </div>
</template>

<script>
import { ref, reactive } from 'vue';
export default {
    name: `Data`,
    setup() {
        // refs accept primitives types like string,bool ..
        const c_firstName = ref('Clarck');
        const c_lastName = ref('Kent');
        const c_heroName = ref('Superman');

        c_firstName.value = 'Diana'
        const greet = `Hello ${c_firstName.value}`;
        const greetHero = `Hello ${c_firstName.value}${c_lastName.value} a.k.a ${c_heroName.value}`;


        // reactive only accept objects
        const state = reactive({
            firstName: 'Princess',
            lastName: 'Diana',
            heroName: 'Wonderwoman'
        })

        const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName}`;

        return {
            c_firstName,
            c_lastName,
            c_heroName,
            greet,
            greetHero,
            reactiveGreetHero
        }
    },
    data() {
        return {
            o_firstName: `Bruc`,
            o_lastName: `Wayne`,
            o_heroName: `Batman`,

        }
    },
}
</script>

<style scoped></style>
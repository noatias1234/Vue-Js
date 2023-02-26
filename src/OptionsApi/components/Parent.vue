<template>
    <div>
        Parent component
        <button @click="showChild = !showChild">Toggle child</button>
        <Childs v-if="showChild" />
    </div>
</template>

<script>
import Childs from './Childs.vue';
export default {
    components: { Childs },
    name: `Parent`,
    data() {
        return {
            showChild: true
        }
    },
    beforeCreate() {
        console.log('Parent before create');
    },
    created() {
        console.log('Parent created');
    },
    beforeMount() {
        console.log('Parent before mount');
    },
    mounted() {
        console.log('Parent mounted');
    },
    beforeUpdate() {
        console.log('Parent before update');
    },
    updated() {
        console.log('Parent updated');
    }
}
</script>

<style scoped></style>
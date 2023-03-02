<template>
    <div>Options API LifeCycle Hooks
    </div>
</template>

<script>
export default {
    name: `LifeCycleO`,
    beforeCreate() {
        console.log('LifeCycleO before create');
    },
    created() {
        console.log('LifeCycleO created');
    },
    beforeMount() {
        console.log('LifeCycleO before mount');
    },
    mounted() {
        console.log('LifeCycleO mounted');
    },
    beforeUpdate() {
        console.log('LifeCycleO before update');
    },
    updated() {
        console.log('LifeCycleO updated');
    }
}
</script>

<style scoped></style>
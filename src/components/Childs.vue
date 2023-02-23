<template>
    <div>

    </div>
</template>

<script>
export default {
    name: `Chils`,
    beforeCreate() {
        console.log('Child before create');
    },
    created() {
        console.log('Child created');
    },
    beforeMount() {
        console.log('Child before mount');
    },
    mounted() {
        console.log('Child mounted');
    },
    beforeUpdate() {
        console.log('Child before update');
    },
    updated() {
        console.log('Child updated');
    }
}
</script>

<style scoped></style>
<template>
    <div>
        <h2>{{ username }}</h2>
    </div>
</template>

<script>

export default {
    name: 'component-F',
    inject: ['username'],
}
</script>

<style scoped></style>
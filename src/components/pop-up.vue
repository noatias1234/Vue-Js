<template>
    <div>
        <h2>This is pop-up window</h2>
        <button @click="$emit('close', 'Hi im Bar')">Close pop up</button>
    </div>
</template>

<script>
export default {
    name: 'pop-up',
    emits: ['close']
}
</script>

<style scoped></style>
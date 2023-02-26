<template>
    <div>
        <h2 @mouseover="increase">Clicked {{ count }} times</h2>
    </div>
</template>

<script>
import counter from '@/mixins/counter';
export default {
    name: `HoverCounter`,
    mixins: [counter]

}
</script>

<style scoped></style>
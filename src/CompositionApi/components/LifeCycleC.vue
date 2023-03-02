<template>
    <div>

    </div>
</template>

<script>
import {
    onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted
} from 'vue'
export default {
    name: `LifeCycleC`,

    //beforeCreate & create been replace by setup method im composition 
    setup() {
        onBeforeMount(() => {
            console.log('LifeCycleC onBeforeMount');
        }),

            onMounted(() => {
                console.log('LifeCycleC mounted');

            }),
            onBeforeUpdate(() => {
                console.log('LifeCycleC onBeforeUpdated');
            }),

            onUpdated(() => {
                console.log('LifeCycleC updated');
            }),
            onBeforeUnmount(() => {
                console.log('LifeCycleC onBeforeUnmounted');
            }),
            onUnmounted(() => {
                console.log('LifeCycleC onUnmounted');
            })
    },
}
</script>

<style scoped></style>
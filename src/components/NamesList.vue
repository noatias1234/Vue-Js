<template>
    <div>
        <h3 v-for="name in names" :key="name.firstName">
            <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
        </h3>
    </div>
</template>

<script>
export default {
    nane: `NamesList`,
    data() {
        return {
            names: [
                {
                    firstName: 'Simon',
                    lastName: 'Kriheli'
                },
                {
                    firstName: 'Vadim',
                    lastName: 'David'
                },
                {
                    firstName: 'Roi',
                    lastName: 'Bar'
                },
            ]
        }
    }
}
</script>

<style scoped></style>
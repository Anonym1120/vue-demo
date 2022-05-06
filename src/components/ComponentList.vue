<template>
<button @click="click">添加元素</button>
<transition-group name="list">
<div v-for="item in items" :key="item">
元素 {{ item }}
</div>
</transition-group>
</template>

<script>

export default {
    data() {
        return {
            items: [1, 2, 3, 4, 5]
        }
    },
    methods: {
        click() {
            this.items.push(this.items[this.items.length-1] +1)
        }
    }
}

</script>

<style scoped>

.list-enter-active,
.list-leave-active {
    transition: all 1s ease;
}

.list-enter-from,
.list-leave-to {
    opacity: 0;
}

.list-move {
    transition: transform 1s ease;
}


</style>
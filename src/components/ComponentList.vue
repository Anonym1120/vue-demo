<template>
<button @click="click">添加元素</button>
<transition-group name="list">
<div v-for="item in items" :key="item">
元素 {{ item }}
</div>
</transition-group>

<hr/>

<button @click="click2">添加元素</button>
<transition-group tag="ul" name="list">
<li v-for="list in lists" :key="list">{{ list }}</li>
</transition-group>

</template>

<script>

export default {
    data() {
        return {
            items: [1, 2, 3],
            lists: [1, 2, 3],
        }
    },
    methods: {
        click() {
            this.items.push(this.items[this.items.length-1] +1)
        },

        click2() {
            this.lists.push(this.lists[this.lists.length-1] +1)
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
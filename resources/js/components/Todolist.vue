

<template>
    <div class="todo">
        <h1 class="title">
            Todo List Vue + Larvel
        </h1>
        <h2>
                Add Todo Item
            </h2>
        <CreateItem />
        <Items />
    </div>
    
</template>

<script>
    import CreateItem from "./CreateItem.vue"
    import Items from "./Items.vue"
    export default {
        components: {
            CreateItem,
            Items
    }
}

</script>


<style scoped>
    .todo{
        display:grid;
        align-items: center;
        justify-content: center;

        text-align: center;
    }
</style>
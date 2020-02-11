<template>
<b-container class="bv-example-row">
    <b-list-group-item>
        <b-row>
            <b-col cols="3">
                <b-form-checkbox 
                    size="lg" type="checkbox"
                    v-on:change="todo.completed=!todo.completed"
                ></b-form-checkbox>
            </b-col>
            <b-col cols="6">
                <strong>{{index + 1}}</strong>
                {{todo.title}}
            </b-col>
            <b-col cols="43">
                <b-button 
                    variant="danger"
                    v-on:click="$emit('remove-todo', todo.id)"
                >&times;</b-button>
            </b-col>
        </b-row>
    </b-list-group-item>
</b-container>  
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true
        },
        index: Number
    }
}
</script>

<style scoped>
    li {
        border: 1px solid#ccc;
        display: flex;
        justify-content: space-between;
        padding: .5rem 2 rem;
        margin-bottom: 1rem;
    }
    .done {
        text-decoration: line-through;
    }
</style>
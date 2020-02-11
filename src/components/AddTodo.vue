<template>
<b-container class="bv-example-row">
  <b-row cols="1" cols-sm="8" cols-md="6" cols-lg="4">
    <b-form v-on:submit.prevent="onSubmit">
        <b-form-input
          id="input-1"
          v-model="title"
          type="text"
        ></b-form-input>
        <b-button type="submit" variant="primary">Submit</b-button>
    </b-form>
  </b-row>
</b-container>
</template>

<script>
export default {
    data() {
        return {
            title: ''
        }
    },
    methods: {
        onSubmit(event) {
            if(this.title.trim()) {
                const newTodo = {
                    id: Date.now(),
                    title: this.title,
                    completed: false,
                }

                this.$emit('add-todo', newTodo)
                this.title = ''
            }
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
        margin: 15px;

    }
    input {
        width: 250px;
        margin-right: 10px;
    }
</style>
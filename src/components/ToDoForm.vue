<template>
    <form @submit.prevent="onSubmit">
        <h2 class="label-wrapper">
            <label for="new-todo-input">
                What needs to be done?
            </label>
        </h2>
        <input
            type="text"
            id="new-todo-input"
            name="new-todo"
            autocomplete="off"
            v-model.lazy.trim="label"
            class="input__lg"
            />
        <button type="submit" class="btn btn__primary btn__lg">
            Add
        </button>
    </form>
</template>


<script>
    export default {
        props : {},
        data () { 
            return {
                label: "",
            };
        },
        methods: {
            onSubmit() {
                this.$emit('emitted-label', this.label);
                this.label = "";
            },
        },
    }
</script>


<style>
</style>
<template>
    <div class="input-box">
        <textarea :name="name" :placeholder="placeholder" @keyup="change_event(v_form)" v-model="v_form"></textarea>
    </div>
</template>

<style>
.input-box textarea {
    border: 1px solid #ccc;
    border-radius: 3px;
    min-width: 300px;
    height: 150px;
    padding: 12px;
}
</style>

<script>
export default {
    name: "TextAreaForm",
    props: {
        name: {
            type: String,
            default: ''
        },
        placeholder: {
            type: String,
            default: '',
        },
        change_event: {
            type: Function,
            default: function() {}
        }
    },
    data() {
        return {
            v_form: '',
        }
    }
}
</script>
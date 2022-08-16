<template>
    <div class="input-box">
        <input type="text" 
            :name="name" 
            :id="id" 
            :placeholder="placeholder"
            class="input-text-base"
            v-model="f_value"
            @keyup="chage_value(f_value)"
        />
        <p v-if="v_require" class="require">必須</p>
    </div>
</template>

<style>
.input-box {
    width: 300px;
    min-width: 150px;
    position: relative;
}
.input-box input[type=text] {
    width: 100%;
    height: 35px;
    font-size: 13px;
    padding-left: 10px;
    border-radius: 3px;
    border: 1px solid #ccc;
    padding-right: 55px;
}
.input-box input[type=text]:focus {
    outline: none;
}
.input-box .require {
    position: absolute;
    background-color: red;
    font-size: 11px;
    padding: 3px 8px;
    color: #fff;
    font-weight: bold;
    border-radius: 4px;
    right: 10px;
    top: 6px;
}
</style>

<script>
export default {
    name: "InputTextForm",
    props: {
        name: {
            type: String,
            default: null,
        },
        id: {
            type: String,
            default: null,
        },
        value: {
            type: String,
            default: ''
        },
        placeholder: {
            type: String,
            default: ''
        },
        v_require: {
            type: Boolean,
            default: false
        },
        chage_value: {
            type: Function,
            default: function() { console.log('chage'); }
        }
    },
    data() {
        return {
            f_value: '',
        }
    },
}
</script>

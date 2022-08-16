<template>
    <div class="input-box">
        <h4>{{ navigate }}</h4>
        <div class="file-count">{{file_count}} 枚選択中</div>
        <input type="file" :name="file_id" :id="file_id" multiple v-on:change="change_file_input" :accept="valid_accept">
        <label :for="file_id">{{ label }}</label>
    </div>
</template>

<style>
.input-box h4 {
    margin-bottom: 5px;
}
.input-box input[type=file] {
    display: none;
}
.input-box label {
    display: block;
    width: 120px;
    height: 35px;
    line-height: 35px;
    font-size: 12px;
    text-align: center;
    border-radius: 3px;
    color: #fff;
    background-color: #1d9bf0;
}
.input-box .file-count {
    font-size: 13px;
    margin-bottom: 3px;
}
</style>

<script>
export default {
    name: "InputFile",
    // props: ['file_id', 'label', 'navigate', 'file_chage_event'],
    props: {
        file_id: {
            type: String,
            default: ''
        },
        label: {
            type: String,
            default: ''
        },
        navigate: {
            type: String,
            default: ''
        },
        file_chage_event: {
            type: Function,
            default: function() {},
        },
        valid_accept: {
            type: String,
            default: '',
        },
    },
    data() {
        return {
            file_count: 0,
        }
    },
    computed: {
    },
    methods: {
        change_file_input: function(files) {
            if (files != undefined) {
                const images = files.target.files;
                this.file_count = images.length;

                this.$props.file_chage_event(files);
            }
        }
    }
}
</script>
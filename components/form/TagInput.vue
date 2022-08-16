<template>
    <div class="input-box">
        <h4>タグ</h4>
        <div class="tag-view" v-if="tags.length > 0">
            <div class="tag" v-for="tag in tags" v-on:click="delete_tag_event(tag)">#{{ tag }}</div>
        </div>
        <input type="text" value="" placeholder="タグ（例: オリジナル 学窓ハクメイ" @keydown.enter="tag_submit_event">
    </div>
</template>

<style>
.input-box .tag-view {
    padding: 10px 0;
}
.input-box .tag-view .tag {
    background-color: #7e97c8;
    display: inline-block;
    font-size: 13px;
    color: #fff;
    padding: 3px 8px;
    border-radius: 4px;
    cursor: pointer;
    margin-right: 8px;
}
</style>

<script>
export default {
    name: "TagInputForm",
    props: {
        name: {
            type: String,
            default: 'tags_input'
        },
        update_tag_event: {
            type: Function,
            default: function() {}
        }
    },
    data() {
        return {
            tags: [],
            v_tag: '',
        }
    },
    methods: {
        tag_submit_event: function(e) {
            /**
             * タグが入力されたときに実行されるメソッド
             */

            if (e.keyCode != 13) return // 日本語入力時キー操作キャンセル
            let tag_value = e.target.value;

            // 空白処理
            tag_value = tag_value.replace('#', '');
            if (tag_value != undefined && tag_value != "" && tag_value.length > 0) {
                this.tags.push(tag_value)
                e.target.value = '';
            }

            this.update_send_data();
        },
        delete_tag_event: function(tag) {
            /**
             * タグ削除イベントメソッド
             */
            const del_idx = this.tags.indexOf(tag);
            this.tags.splice(del_idx, 1);

            this.update_send_data();
        },
        update_send_data: function() {
            /**
             * 送信データの更新メソッド
             */

            let tag_cocate = '';
            for (let tag of this.tags) {
                tag_cocate += tag + ','
            }
            
            this.$props.update_tag_event(this.tags)
        }
    }
}
</script>
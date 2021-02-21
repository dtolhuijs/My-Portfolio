<template>
    <section>
        <vue-editor v-model="content"></vue-editor>
    </section>
</template>

<script>
import { VueEditor } from "vue2-editor";
import axios from "axios";
export default {
    components: {
        VueEditor
    },

    data() {
        return {
            content: "",
            customToolbar: [
                ["bold", "italic", "underline"],
                [{ list: "ordered" }, { list: "bullet" }],
                // ["image", "code-block"]
            ]
        };
    },

    watch: {
        content() {
            EventBus.$emit('editor-content-change', this.content)
        }
    }
};
</script>


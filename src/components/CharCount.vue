<template>
    <div id="char-count">
        <p>{{ params.label }}: {{ count }}</p>
    </div>
</template>

<script lang="ts">
    import { defineComponent, PropType } from 'vue'

    // Use one params props prop to encapsulate inputText and label
    export interface CharCountParams {
        label: string
        inputText: string
    }

    export default defineComponent({
        name: 'CharCount',
        props: {
            params: {
                type: Object as PropType<CharCountParams>,
                required: true
            }
            /*
            inputText: {
                type: String,
                required: true
            },
            label: {
                type: String,
                required: true
            }   
            */
        },
        computed: {
            count(): number {
                return this.params.inputText.length
            }
        }
    })
</script>
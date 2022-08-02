<template>
    <Form @onSubmit="handleSubmit" />
    <List @onRemove="handleRemove" :items="notes"/>
</template>

<script>
import Form from '@/components/Notes/Form.vue'
import List from '@/components/Notes/List.vue'

export default {
    components: { Form, List },
    data() {
        return {
            notes: [
                {
                    title: 'learn Vue 3',
                    tags: ['work']
                },
                {
                    title: 'Finish Vue 3',
                    tags: ['work', 'home']
                },
                {
                    title: 'hello Vue 3',
                    tags: []
                },
            ],
        }
    },
    methods: {
        handleSubmit(note) {
            this.notes.push(note)
            // console.log(note)
        },
        handleRemove(index) {
            this.notes.splice(index, 1)
        }
    }
}
</script>
<template>
    <form>
        <input type="text" v-model="message">
        <button type="button" @click="submit">點我送出</button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                message: ''
            }
        },

        methods: {
            submit() {
                axios.post('/send', {
                    message: this.message,
                })
            }
        }
    }
</script>
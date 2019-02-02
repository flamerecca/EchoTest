// Receiver.vue
<template>
    <ul>
        <li v-for="message in messages" :key="message">{{ message }}</li>
    </ul>
</template>

<script>
    export default {
        data () {
            return {
                messages: [
                    'Hello'
                ]
            }
        },

        mounted() {
            Echo.channel('mychannel')
                .listen('BroadcastEvent', (e) => {
                    this.messages.push(e.message);
                });
        }
    }
</script>
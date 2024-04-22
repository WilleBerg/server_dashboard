<style scoped>

</style>
<template>
    <div>
        <a v-bind:href="this.ip" target="_blank"> {{this.name}}</a>
    </div>
</template>
<script>
export default {
    data() {
        return {
            
        }
    },
    props: {
        ip: {
            required: true,
        },
        name: {
            required: true,
        }

    }
}
</script>


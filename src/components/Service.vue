<style scoped>
img {
    width: var(--service-image-size);
    height: var(--service-image-size);
    transition: transform 0.5s ease;
    /* Add transition effect */
}

img:hover {
    /* width: var(--service-image-size-hover);
    height: var(--service-image-size-hover); */
    transform: scale(1.2);
}
</style>
<template>
    <div>
        <a v-bind:href="this.ip" target="_blank">
            <img :src="this.icon" />
        </a>
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
        },
        icon: {
            required: true,
        }
    }
}
</script>

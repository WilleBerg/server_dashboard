<style scoped>
img {
    width: 8rem;
    height: 8rem;
    transition: transform 0.5s ease;
    /* Add transition effect */
}

img:hover {
    /* width: var(--service-image-size-hover);
    height: var(--service-image-size-hover); */
    transform: scale(1.2);
}

@media screen and (max-width: 700px) {
    img {
        width: 19dvw;
        height: 19dvw;
        ;
        transition: transform 0.5s ease;
        /* Add transition effect */
    }
}
</style>
<template>
    <a v-bind:href="this.ip" target="_blank">
        <img :src="this.icon" />
    </a>
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

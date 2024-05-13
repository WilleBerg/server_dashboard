<script>
export default {
    data() {
        return {
            formData: {
                search: ''
            }
        };
    },
    methods: {
        handleSubmit(event) {
            // Prevent the default form submission
            event.preventDefault();
            console.log('Form submitted with data:', this.formData.search);
            // Simulate a mouse click:
            let url = "https://duckduckgo.com/?q=" + this.formData.search;
            console.log(url);

            window.location.href = url;
        }
    }
};
</script>

<template>
    <div class="search" style="margin-bottom: 30px;">
        <form @submit="handleSubmit">
            <input class="form" placeholder="Search duckduckgo" type="text" name="search" v-model="formData.search">
        </form>
    </div>
</template>

<style scoped>
.search {
    display: inline-block;
    position: relative;
    background-color: var(--clr-input);
    border: 1px solid white;
}

input {
    padding: 10px 10vw 10px 1vw;
}
</style>
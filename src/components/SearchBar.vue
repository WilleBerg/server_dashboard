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
            <input placeholder="Search duckduckgo" type="text" name="search" v-model="formData.search">
            <button>
                Search
            </button>
        </form>
    </div>
</template>

<style scoped></style>
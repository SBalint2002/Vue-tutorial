<template>
    <div class="container">
        <h1 class="emphasize">Page Title</h1>
        <p>Content</p>
    </div>
</template>

<script>

export default {
    props: {
        page : {
            type: Object,
            default(rawProps) {
                //Ha undefined akkor ez az alapértelmezett érték
                return {
                    pageTitle: '',
                    content: ''
                };
            }
         }
    }
}
</script>
<style scoped>
.emphasize {
    color: blue;
}
</style>
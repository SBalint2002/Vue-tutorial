<template>
    <div v-if="page" class="container">
        <h1 class="emphasize">{{page.pageTitle}}</h1>
        <p>{{page.content}}</p>
    </div>
</template>

<script>

export default {
    props: ['index'],
    created() {
        this.page = this.$pages.getSinglePage(this.index);

        //vagy így vagy a watch-al és props-al
        // this.$watch(() => this.$route.params, (newParams, prevParams) => {
        //     this.page = this.$pages.getSinglePage(newParams.index);
        // });
    },
    data() {
        return {
            page: null
        };
    },
    watch: {
        index(newIndex, oldIndex) {
            this.page = this.$pages.getSinglePage(newIndex);
        }
    }
}
</script>
<style scoped>
.emphasize {
    color: blue;
}
</style>
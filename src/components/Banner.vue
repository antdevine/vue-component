<template>
    <div>
        <h2 v-if="title" v-html="title" />
        <slot></slot>
        
    </div>
</template>

<script>

export default {
    name: 'Banner',
    props: {
        title: {
            type: String,
            required: false
        }
    }
}

</script>

<style scoped>
    h2 {
        color: yellowgreen;
        background: blue;
    }
</style>
<template>
    <div v-if='revele'>
        Je suis la modal
        <button v-on:click='toggleModal'>X</button>
    </div>
</template>

<script>
export default {
    name: 'Modal',
    props: ['toggleModal', 'revele'],
    methods: {

    }
}
</script>

<style scoped>

</style>
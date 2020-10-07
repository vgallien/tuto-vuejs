<template>
    <div v-if='revele' class="fenetre-modal">
        <div class="overlay" v-on:click='toggleModal'></div>
        <div class="fenetre-content">
            Je suis la modal
            <button v-on:click='toggleModal'>X</button> 
        </div>
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
    .fenetre-modal {
        position: fixed;
        top: 0; right: 0; left: 0; bottom: 0;
        height: 100%;
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .overlay {
        position: absolute;
        top: 0; right: 0; left: 0; bottom: 0;
        height: 100%;
        width: 100%;
        background-color: rgba(0, 0, 0, 0.5);
    }
    .fenetre-content {
        position: relative;
        width: 60%;
        bottom: 10%; 
        min-height: 150px;
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: #fff;
    }
    button {
        position: absolute;
        top: 20px;
        right: 20px;
    }
</style>
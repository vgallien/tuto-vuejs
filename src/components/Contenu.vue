<template>
    <div class="container mt-5">

        <h1>{{ titre }}</h1>
        <div class="btn btn-outline-primary mr-2" v-on:click="toggleOng1">Onglet 1</div>
        <div class="btn btn-outline-primary" v-on:click="toggleOng2">Onglet 2</div>
        <div class="onglets card mb-5" v-if="toggle1">
            <texte1 class="p-5"></texte1>
        </div>
        <div class="onglets card mb-5" v-if="toggle2">
            <texte2 class="p-5"></texte2>
        </div>
    </div>
</template>

<script>

    import Texte1 from './Texte1'
    import Texte2 from './Texte2'

    export default {
        name: 'Contenu',
        data() {
            return {
                myArr: [
                    { titre: 'Inception', date: 2010 },
                    { titre: 'Avatar', date: 2009 },
                    { titre: 'Seven', date: 1955 }
                ],
                txt: 'Hello World',
                titre: 'Je suis le titre',
                toggle1: true,
                toggle2: false
            }
        },
        methods: {
            toggleOng1: function() {
                this.toggle1 = true
                this.toggle2 = false
            },
            toggleOng2: function() {
                this.toggle1 = false
                this.toggle2 = true
            }
            // changementTitre: function(nvTitre) {
            //     this.titre = nvTitre
            // }
        },
        components: {
            'texte1': Texte1,
            'texte2': Texte2
        }
    }
</script>

<style>
    h1 {
        margin-top: 100px !important;
    }
</style>
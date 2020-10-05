<template>
    <div class="header-top">
        <p>{{ titre }}</p>
    </div>
</template>

<script>

    import {bus} from '../main'

    export default {
        name: 'Header',
        data() {
            return {
                titre: 'Mon titre de base'
            }
        },
        beforeCreate() {
            console.log('Il va être crée');
        },
        created() {
            console.log('Le composant est crée !');
            bus.$on('changeTitre', (data) => {
                this.titre = data
            })
        },
        beforeMount() {
            console.log('Il va être monté dans le DOM !');
        },
        mounted() {
            console.log('Il est intégré dans le DOM !');
        },
        beforeUpdate() {
            console.log('Avant mise à jour !');
        },
        updated() {
            console.log('Mis à jour !');
        }
    }

</script>

<style scoped>
    .header-top {
        position: fixed;
        top: 0;
        height: 50px;
        width: 100%;
        color: #f1f1f1;
        font-size: 24px;
        line-height: 50px;
        text-align: center;
        background: #333;
    }
</style>

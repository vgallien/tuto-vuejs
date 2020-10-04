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
        created() {
            bus.$on('changeTitre', (data) => {
                this.titre = data
            })
        }
    }

</script>

<style>
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

<template>
    <div>
        <ul class="liste mt-5">
            <li v-for="(film, index) in myArr" v-bind:key="index">
                <div class="card">
                    <div class="card-body">
                        Titre : {{ film.titre }} <br />
                        Date : {{ film.date }}
                    </div>
                </div>
            </li>
        </ul>
        <p>{{ txt }}</p>
        <div class="btn btn-danger mt-2" v-on:click="supprFilm">Supprime le film</div>
        <div class="btn btn-danger mt-2 ml-2" v-on:click="supprTxt">Supprime le txt</div>
        <div class="btn btn-danger mt-2 ml-2" v-on:click="changeTitre">Modifie le titre</div>
    </div>
</template>

<script>

import {bus} from '../../main'

export default {
    name: 'Liste',
    data() {
        return {
            fruits: ['Orange', 'Papaye', 'Fraise']
        }
    },
    methods: {
        supprFilm: function() {
            this.myArr.pop()
        },
        supprTxt: function() {
            this.txt = ""
        },
        changeTitre: function() {
            // this.$emit('changeTitre', 'Mon nouveau titre')
            bus.$emit('changeTitre', 'Titre changé avec le bus !')
        }
    },
    props: ['myArr', 'txt']
}
</script>

<style scoped src="./Liste.css">
</style>
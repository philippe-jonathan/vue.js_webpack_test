<template>
    <div id='departements'>
        <h1>coucou</h1>
        <ul>
            <li v-for="d in departements">{{ d.nom }}</li>
        </ul>
    </div>

</template>

<script>
import $ from 'jquery'

export default {
    name: 'departements',
    data() {
        return {
            departements: []
        }
    },
    created: function() {
        $.ajax('https://geo.api.gouv.fr/departements')
        .done( function(d) {
            this.departements = d
        }.bind(this))
    }
}
</script>

<style>
 #departements {
     text-align: center;
 }
</style>

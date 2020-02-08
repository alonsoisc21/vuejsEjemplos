<template>
    <div>
        <h1>Galería de fotos</h1>
        <router-link :to="{ name:'fotos', params:{id:item} }" v-for="(item,index) of fotosArreglo" :key="index">
            <button>Foto {{item}}</button>
        </router-link>
        <Foto/>
        <button v-on:click="home">Home</button>
        <button v-on:click="anterior">Anterior</button>
        <button v-on:click="siguiente">Siguiente</button>
    </div>
</template>
<script>
import Foto from "@/components/Fotografia.vue"
export default {
    name: 'Fotos',
    components:{
        Foto
    },
    data(){
        return{
            fotosArreglo:[1,2,3,4,5]
        }
    },
    methods:{
        home(){
            this.$router.push('/')
        },
        anterior(){
            this.$router.go(-1)
        },
        siguiente(){
            this.$router.go(1)
        }
    }
}
</script>
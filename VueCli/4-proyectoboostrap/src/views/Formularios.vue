<template>
    <div class="mt-5">
        <h1>Formularios</h1>
        <form>
            <b-row>
                <b-col md="3">
                    <b-form-input type="text" v-model="text" placeholder="" :state="comprobar"></b-form-input>
                    <small>Minimo 3 caracteres</small>
                    <div class="mt-2">Value: {{ text }}</div>
                </b-col>
                <b-col md="3">
                    <b-form-select v-model="select" :options="animales"></b-form-select>
                    <p>Selección: {{select}}</p>
                </b-col>
                <b-col md="3">
                    <b-form-radio-group v-model="radio" :options="animalesRadio"></b-form-radio-group>
                    <p>Selección: {{radio}}</p>
                </b-col>
                <b-col md="3">
                    <b-form-checkbox-group v-model="check" :options="animalesRadio"></b-form-checkbox-group>
                    <p>Selección: {{check}}</p>
                </b-col>
            </b-row>            
        </form>
    </div>
</template>
<script>
export default {
    name:'Formularios',
    data(){
        return{
            text:'',
            select: null,
            animales:[
                {value:null, text:'Seleccione una opción'},
                {value:'perro', text:'Perroooo'},
                {value:'gato', text:'Gatooooooooo'},
                {value:'pato', text:'Patoooo'}
            ],
            radio:'',
            animalesRadio:[
                {value:'perro', text:'Perroooo'},
                {value:'gato', text:'Gatooooooooo'},
                {value:'pato', text:'Patoooo'}
            ],
            check:[]
        }
    },
    computed:{
        comprobar(){
            return this.text.length > 2 ? true : false
        }
    }
}
</script>